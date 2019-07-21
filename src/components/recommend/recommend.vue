<template>
  <div class="recommend">
    <ul>
      <router-link tag="li"
                   class="item border-bottom"
                   v-for="(item,index) of recommendList"
                   :key="index"
                   :to="'/detail/' + item.id">
          <div class="free"></div>
          <div class="job">
            <div>
              <div class="jobName">{{item.jobName}}</div>
              <div class="jobIncome">{{item.jobIncome}}</div>
            </div>
            <div>
              <div class="comImg"><img  class="img" :src="item.comImg"></div>
              <div class="comName">{{item.comName}}</div>
              <div class="date">{{item.date}}</div>
            </div>
          </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  props: {recommendList: Array}

}
</script>

<style scoped>
  .recommend{
    float:left;
    width:100%;
  }
  .item{
    float:left;
    width:100%;
  }
  .job{
    margin-right: .1rem;
    margin-left:.1rem;
  }
 .free{
   width:100%;
   height:.14rem;
   background-color: #eaeaea;
 }
 .comImg{
   width:.8rem;
   height:.8rem;
 }
  .img{
    width:100%;
    height:100%
  }
  .jobName{
    float:left;
    font-weight: bold;
    margin-top: .2rem;
  }
  .comName{
    float:left;
    margin-left:.9rem;
    margin-bottom: .2rem;
  }
   .date{
    float:right;
  }
  .jobIncome{
    float:right;
    margin-top: .2rem;
  }
</style>
