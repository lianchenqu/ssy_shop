<template>
  <div id="app">
    <router-view></router-view>
    <!-- $route 当前路由 -->
    <FooterGuide v-show='$route.meta.showFooter'></FooterGuide>
  </div>
</template>

<script>
  import FooterGuide from './components/FooterGuide/FooterGuide.vue'
  import {reqFoodType} from './api'


  export default {

    components:{
      FooterGuide,

    },

    async mounted(){
      const result = await reqFoodType()
      console.log(result)
      
    },

  }
</script>

<!-- <style scoped>
  body{
    margin:0
  }
  .app{
    width: 100%;
    height: 100%;
    background:#f5f5f5;
    color: red;
  }
</style> -->
<style lang="stylus" rel="stylesheet/stylus">
  #app
    width: 100%;
    height: 100%;
    background: #f5f5f5;
</style>
