<template>
  <div id="app">
      <el-row type='flex' justify="center"  align="middle" class="top-nav">
        <el-col :span="4" :push=".5">
          <logo></logo>
           
        </el-col>
        <el-col :span="6" :offset="13" :pull=".5">

            <top-nav></top-nav>
        </el-col>
      </el-row>
      

  </div>
</template>

<script>
    import TopNav from './components/nav'
    import Logo from './components/logo'
    export default {
        name: 'app',
        components: {
            TopNav,
            Logo
        }
    }
</script>

<style>
    body {
        margin: 0;
        padding: 0;
    }
    .top-nav{
        /*height:80px;*/
        box-shadow: 0 0 4px rgba(0,0,0,0.25);
    }
</style>