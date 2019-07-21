<template>
  <div class="Kinds">
      <div class="kinds" v-for="(item,index) in kinds.list" :key="index"
                                              :style="'width:'+item_width">
        <div >
          <img class="kindsImg" :src='item.path'>
        </div>
        <div class="kindsText"> {{item.text}}</div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'kinds',
  data () {
    return {
      'kinds': {
        'list': [{
          'path': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
          'text': '前端'
        },
        {
          'path': 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
          'text': '软件'
        },
        {
          'path': 'http://img1.qunarzz.com/piao/fusion/1611/d0/e09575e66f4aa402.png',
          'text': '广告'
        },
        {
          'path': 'http://img1.qunarzz.com/piao/fusion/1611/59/569d3c096e542502.png',
          'text': '招聘'
        },
        {
          'path': 'http://img1.qunarzz.com/piao/fusion/1611/17/4bd370f3eb1acd02.png',
          'text': '市场'
        }
        ]
      }
    }
  },
  computed: {
    item_width () {
      let length = this.kinds.list.length
      switch (length) {
        case 1:
          return '100%'
        // break
        case 2:
          return '50%'
        // break
        case 3:
          return '33.3%'
        // break
        case 4:
          return '25%'
        // break
        case 5:
          return '20%'
        // break
        default:
          break
      }
    }
  }
}
</script>

<style scoped>
  .Kinds{
    margin:.14rem 0 0 0 ;
  }
  .kinds{
    float:left;
  }
  .kindsImg{
    width:.6rem;
    height:.6rem;
  }
  .kindsText{
    margin:.06rem;
  }
</style>
