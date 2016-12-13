<template>
  <div id="app">
   <TopNav></TopNav>
   <EditContent></EditContent> 
   <!--<BottomFooter></BottomFooter>-->
  </div>
</template>

<script>
    import TopNav from './components/top-nav/top-nav'
    import EditContent from './components/edit-content/edit-content'
    import BottomFooter from './components/bottom-footer/bottom-footer'
    export default {
        name: 'app',
        components: {
            TopNav,
            EditContent,
            BottomFooter
        }
    }
</script>

<style>
  html, body{
  height:100%;
}
    body {
        margin: 0;
        padding: 0;
        min-width:1300px;
        font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    }
    #app{
        height:100%;
    }
</style>