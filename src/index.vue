<template>
  <div class="wrapper">
    
    <!--<text style="font-size:40px;">更改入口文123件</text>-->
    <xxy-tab-bar></xxy-tab-bar>
    
  </div>
</template>

<script>
  
  import xxyTabBar from './components/xxyTabBar.vue'
  export default {
    data () {
      return {
       
      }
    }, 
    components:{
      xxyTabBar
    }
  }
</script>

<style scoped>
  .wrapper {
    /*justify-content: center;
    align-items: center;*/
  }

</style>
