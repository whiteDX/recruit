<template>
  <div>
    <HomeHeader class="header" ></HomeHeader>
    <HomeSwiper :swiperList="swiperList"></HomeSwiper>
    <HomeKinds></HomeKinds>
    <HomeRecommend :recommendList="recommendList"></HomeRecommend>
    <HomeFooter class="foot"></HomeFooter>
  </div>
</template>

<script>
import HomeFooter from '@/components/footer/Footer.vue'
import HomeSwiper from '@/components/swiper/swiper.vue'
import HomeRecommend from '@/components/recommend/recommend.vue'
import HomeHeader from './components/header.vue'
import HomeKinds from './components/kinds.vue'
import axios from 'axios'

export default {
  name: 'home',
  components: {
    HomeFooter,
    HomeSwiper,
    HomeHeader,
    HomeKinds,
    HomeRecommend
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      recommendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      axios.get('/static/data/index.json').then(this.getHomeInfoSucc)// 通过url获取到数据并执行getHomInfoSucc
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.swiperList = data.swiperList
        this.recommendList = data.recommendList
      }
    }
  }
}
</script>

<style scoped>
  .foot{
    position:fixed;
    z-index:40;
    width:100%;
    bottom:.2rem;
  }
  .header{
    margin-top:.2rem;
  }

</style>
