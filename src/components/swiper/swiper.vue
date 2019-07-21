<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper" class="swiper">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img"  alt="" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {swiperList: Array},
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      }
    }
  },
  computed: {
    showSwiper () {
      return this.swiperList.length
    }
  }
}
</script>
<style scoped>
  .swiper-pagination-bullet-active{
    background:#ffffff
  }
  .wrapper{
    overflow:hidden;
    width:100%;
    height:100%;
  }

    .swiper-img{
      width:100%;
      height:50%;
      border-radius: 5px;
    }
  .swiper{
    margin:.14rem .14rem 0 .14rem;
  }

</style>
