<template>
  <div  ref="wrapper" >
    <div class="content">
      <div class="job">
        <div class="jobName">{{jobName}}</div>
        <div class="jobIncome">{{jobIncome}}</div>
      </div>
      <div class="com">
          <img class="img" :src="comImg">
          <p class="content comName">{{comName}}</p>
      </div>
      <div class="jobdesc">
        <p class="jobdescfont">职位描述</p>
        <div>
        <p  class="positionStatement"   v-for="(item,index) of  positionStatement" :key="index">{{item.content}}</p>
        </div>
        <div>
        </div>
          <p class="jobRquire"  v-for="(item ,index) of  jobRquire" :key="index">{{item.content}}</p>
      </div>
      </div>
      <div class="comPosition">
        <p class="left">公司地址</p>
        <div class="left comPositionFont">{{comPosition}}</div>
      </div>
    </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  name: 'DetailContent',
  props: {
    jobName: String,
    jobIncome: String,
    comImg: String,
    comPosition: String,
    comName: String,
    date: String,
    positionStatement: Array,
    jobRquire: Array
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper, {})
  }
}
</script>
<style scoped>
  .content{
    display:flex;
    flex-direction: column;
    overflow: hidden;
    margin-top:.5rem;
    margin-bottom:.5rem;
  }
  .positionStatement,.jobRquire{
    margin-top: .2rem;
    margin-left: .2rem;
  }
  .job{
    width: 100%;
    float:left;
  }
  .jobName{
    font-size: .36rem;
    font-weight: bold;
    float: left;
  }
  .jobIncome{
    font-size: .32rem;
    color:red;
    float:right;
  }
  .com{
    margin-top: .5rem;
    width:100%;
  }
  .img{
    float:left;
    width:.8rem;
    height:.8rem;
    margin-top:.3rem;
  }
  p{
    text-align: left;
    line-height: .52rem;
  }
  .comName{
    float:left;
    margin-left:.3rem;
  }
  .jobdescfont{
    font-size: .30rem;
    font-weight: bold;
  }
  .left{
    float:left;
  }
  .comPosition{
    margin-top:.2rem;
    float:left;
  }
  .comPositionFont{
    margin-left:.2rem;
    margin-top: .14rem;
  }
</style>
