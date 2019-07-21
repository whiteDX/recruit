<template>
  <div>
    <city-header class="header"></city-header>
    <city-list  :cities="cities"
                :hot="hotCities"
                :letter="letter"></city-list>
    <CityAlphabet :cities="cities"
                  @change="handleLetterChange"></CityAlphabet>
  </div>
</template>
<script>
import CityHeader from './components/Header'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  mounted () {
    this.getCityInfo()
  },
  methods: {
    getCityInfo () {
      axios.get('/static/data/city.json')
        .then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    }
  }
}
</script>
<style>

</style>
