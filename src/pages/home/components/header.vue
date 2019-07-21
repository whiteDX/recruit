<template>
  <div class="header">
    <router-link to="/city">
      <div class="headerLeft">
        <div class="headerfont">
          {{this.city}}
        </div>
        <span class="iconfont iconfont1">&#xe600;</span>
      </div>
    </router-link>
    <div class="headerRight">
      <span class="iconfont iconfont2">&#xe614;</span>
    </div>
    <div class="headerCenter">
      <span class="rec">推荐</span>
      <span class="find">发现</span>
    </div>

  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'Homeheader',
  computed: {
    ...mapState(['city'])
  },
  methods: {

  }
}
</script>

<style scoped>
  .headerfont{
    height:.5rem;
    line-height:.5rem;
    width:.64rem;
    float:left;
  }
  .iconfont1{
    font-size: 5px;
    line-height:.5rem;
    float:left;
  }
  .headerCenter{
    line-height:.5rem;
    margin:0 auto;
    width:1.4rem;
  }
  .rec{
    line-height:.5rem;
  }
  .find{
    line-height:.5rem;
  }
.iconfont2{
  float:right;
  line-height:.5rem;
  margin:0 .28rem 0 0;
}
</style>
