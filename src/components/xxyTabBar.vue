<template>
    <div class="xxyTabBar">
        <wxc-tab-bar :tab-titles="tabTitles"
                :tab-styles="tabStyles"
                title-type="icon"
                @wxcTabBarCurrentTabSelected="wxcTabBarCurrentTabSelected">
        <!-- 第一个页面内容-->
        <div class="item-container" :style="contentStyle">
            <xxy-header title="首页" rightTex="搜索"></xxy-header>
            <text>热议广场</text>
        
        </div>

        <!-- 第二个页面内容-->
        <div class="item-container" :style="contentStyle">
            <xxy-header title="排行榜" rightTex="更多"></xxy-header>
            <text>游戏排行</text>
        </div>

        <!-- 第三个页面内容-->
        <div class="item-container" :style="contentStyle">
            <xxy-header title="搜索" leftTex="前往" rightTex="更多"></xxy-header>
            <text>搜索游戏</text>   
        </div>

        <!-- 第四个页面内容-->
        <div class="item-container" :style="contentStyle">
            <xxy-header title="个人中心" leftTex="前往" rightTex="更多"></xxy-header>
            <text>我的主页</text>
        </div>
    </wxc-tab-bar>
    </div>
  
</template>

<style scoped>
.xxyTabBar{
    position:fixed;
    left:0;right:0;top:0;bottom:0;
}
  .item-container {
    width: 750px;
    background-color: #f2f3f4;
    align-items: center;
    /*justify-content: center;*/
  }

</style>
<script>
  import { WxcTabBar, Utils } from 'weex-ui';
  import Config from './config'
  import xxyHeader from './xxyHeader.vue'

  export default {
    components: { WxcTabBar,xxyHeader },
    data: () => ({
      tabTitles: Config.tabTitles,
      tabStyles: Config.tabStyles
    }),
    created () {
      const tabPageHeight = Utils.env.getPageHeight();
      // 如果页面没有导航栏，可以用下面这个计算高度的方法
      // const tabPageHeight = env.deviceHeight / env.deviceWidth * 750;
      const { tabStyles } = this;
      this.contentStyle = { height: (tabPageHeight - tabStyles.height) + 'px' };
      console.log(this.contentStyle)
    },
    methods: {
      wxcTabBarCurrentTabSelected (e) {
        const index = e.page;
        // console.log(index);
      }
    }
  };
</script>