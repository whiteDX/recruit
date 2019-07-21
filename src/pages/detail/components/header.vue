<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont header-back">&#xe60e;</div>
    </router-link>
    <p class="text">职位详情</p>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader'
}
</script>
<style scoped>
  .header{
    width:100%;
    line-height: .5rem;
    border-bottom:.01rem solid #eaeaea;
    position:fixed;
    padding-bottom: .1rem;
    top:0;
    left:0;
    background-color: #ffffff;
  }
  .header-back{
    float:left;

  }
  .text{
    margin-right:.3rem;
    text-align:center;
    font-size: .35rem;
  }

</style>
