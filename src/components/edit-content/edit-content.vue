<template>
       <el-row type='flex' justify="center"  align="middle" class="edit-content">
        <el-col :span="4" :push=".5">
          
        <LeftSlide></LeftSlide>
        </el-col>
        <el-col :span="9" >
          
           <MiddleInfo></MiddleInfo>
        </el-col>
        <el-col :span="10"  :pull=".5">

        <RightEdit></RightEdit>
        </el-col>
      </el-row>

</template>

<script>
    import LeftSlide from './left-slide'
    import MiddleInfo from './middle-info'
    import RightEdit from './right-edit'
    export default {
        components: {
            LeftSlide,
            MiddleInfo,
            RightEdit
        }
    }
</script>
<style scoped>
    .edit-content{
        height:100%;
    }
</style>
