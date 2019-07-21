<template>
<div class="footer">
  <button class="btn">投个简历</button>
</div>
</template>
<script>
export default {
  name: 'DetailFooter'
}
</script>
<style scoped>
  .footer{
    height: .5rem;
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #ffffff;
    padding-top: .1rem;
    border-top: .01rem solid #eaeaea;
  }
  .btn{
    color:#ffffff;
    background-color: #25a4bb;
    width:50%;
  }
</style>
