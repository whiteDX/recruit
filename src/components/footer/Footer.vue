<template>
  <div>
    <div class="footer">
      <div v-for="(item,index) in tabBar.list" :class="'footer_item ' + (item.size=='big'?'big_item':'')  "
                                               :style="'width:'+item_width"
                                                @click="change_nav(index, item)"
                                                :key="index">
        <img class='image' :src="index==now_index?item.selectedIconPath:item.iconPath" mode="">
        <div > {{item.text}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Footer',
  data () {
    return {
      'tabBar': {
        'color': '#7a7e83',
        'selectedColor': '#7558ff',
        'backgroundColor': '#ffffff',
        'list': [{
          'pagePath': 'pages/home/Home.vue',
          'text': '首页',
          'code': 'home', // ???有什么用
          'iconPath': 'static/img/icons/icon-home.png',
          'selectedIconPath': 'static/img/icons/icon-home-selected.png'
        }, {
          'pagePath': 'pages/message/Message.vue',
          'text': '消息',
          'code': 'message',
          'iconPath': 'static/img/icons/icon-message.png',
          'selectedIconPath': 'static/img/icons/icon-message-selected.png'
        }, {
          'pagePath': 'pages/community/Community.vue',
          'text': '社区',
          'code': 'blind',
          'iconPath': 'static/img/icons/icon-community.png',
          'selectedIconPath': 'static/img/icons/icon-community-selected.png'
        },
        {
          'pagePath': 'pages/service/Service.vue',
          'text': '服务',
          'code': 'svc',
          'iconPath': 'static/img/icons/icon-service.png',
          'selectedIconPath': 'static/img/icons/icon-service-selected.png'
        },
        {
          'pagePath': 'pages/user/User.vue',
          'text': '我的',
          'code': 'user',
          'iconPath': 'static/img/icons/icon-my.png',
          'selectedIconPath': 'static/img/icons/icon-my-selected.png'
        }]
      },
      page_index: 0
    }
  },
  methods: {
    change_nav (index, item) {
      this.page_index = index
      this.$emit('change', item, index)// 自动触发父组件的change事件
    }
  },
  computed: {
    item_width () {
      let length = this.tabBar.list.length
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
    },
    now_index () {
      return this.page_index
    }
  }
}
</script>

<style scoped>
  .footer{
    height: 5px;//值待设置
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #ffffff;
    color: #fff;
  }
  .footer_item{
    float: left;
    width: 33.3%;
    text-align: center;

  }
  .footer_item image{
    width: 10px;
    height: 10px;
  }
  .footer_item.big_item{
    position: relative;
    top: -40px;
  }
  .footer_item.big_item image{
    width: 20px;
    height: 20px;
  }
  .footer{
    color:#181E30;
  }
  .image{
    width:30px;
    height:30px;
  }

</style>
