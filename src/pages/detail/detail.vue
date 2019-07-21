<template>
  <div>
    <DetailHeader></DetailHeader>
    <DetailContent class="content"
                   :jobName="jobName"
                   :jobIncome="jobIncome"
                   :comImg="comImg"
                   :comPosition="comPosition"
                   :comName="comName"
                   :date="date"
                   :jobRquire="jobRquire"
                   :positionStatement="positionStatement"
    ></DetailContent>
    <DetailFooter></DetailFooter>
  </div>
</template>
<script>
import DetailHeader from './components/header.vue'
import DetailFooter from './components/footer.vue'
import DetailContent from './components/content.vue'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailHeader,
    DetailFooter,
    DetailContent
  },
  data () {
    return {
      jobName: '',
      jobIncome: '',
      comImg: '',
      comPosition: '',
      comName: '',
      date: '',
      positionStatement: [],
      jobRquire: []
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/static/data/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data[this.$route.params.id - 1]
        this.jobName = data.jobName
        this.jobIncome = data.jobIncome
        this.comImg = data.comImg
        this.comPosition = data.comPosition
        this.comName = data.comName
        this.date = data.date
        this.positionStatement = data.positionStatement
        this.jobRquire = data.jobRquire
      }
    }
  },
  activated () {
    this.getDetailInfo()
  }
}
</script>
<style scoped>

</style>
