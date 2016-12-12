<template>
<el-menu default-active="1" class="top-menu" mode="horizontal" @select="handleSelect">
  <el-menu-item index="1" >数据总览</el-menu-item>
  <el-menu-item index="2">数据统计</el-menu-item>
    <el-submenu index="3">
    <template slot="title">设置中心</template>
    <el-menu-item index="3-1">全局配置</el-menu-item>
    <el-menu-item index="3-2">标签</el-menu-item>
    <el-menu-item index="3-3">关于</el-menu-item>
  </el-submenu>
</el-menu>
</template>
<script>
  export default {
    methods: {
      handleSelect(key, keyPath) {
        console.log(key, keyPath);
      }
    }
  }
</script>
<style scoped>
    .top-menu{
    background:#fff;   
    }
    
</style>