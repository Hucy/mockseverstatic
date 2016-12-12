<template>
       <el-row type='flex' justify="center"  align="middle" class="top-nav">
        <el-col :span="4" :push=".5">
          <logo></logo>
           
        </el-col>
        <el-col :span="6" :offset="13" :pull=".5">

            <top-nav></top-nav>
        </el-col>
      </el-row>

</template>

<script>
    import TopNav from './nav'
    import Logo from './logo'
    export default {
        components: {
            TopNav,
            Logo
        }
    }
</script>
<style scoped>
    .top-nav{
        /*height:80px;*/
        box-shadow: 0 0 4px rgba(0,0,0,0.25);
    }
</style>
