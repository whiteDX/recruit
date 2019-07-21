<template>
  <div class="header">
    <router-link to="/">
    <div class="iconfont header-back">&#xe60e;</div>
    </router-link>
      <p class="text">选择城市</p>
  </div>
</template>
<script>
export default {
  name: 'CityHeader'
}
</script>
<style scoped>
  .header{
    width:100%;
    line-height: .5rem;
    margin-top: .2rem;

  }
  .header-back{
    float:left;

  }
  .text{
    margin-right:.3rem;
    text-align:center;
  }
  .text-p{

  }
</style>
