<template>
       <el-row type='flex' justify="center"  align="top" class="edit-content">
        <el-col :span="4" :push=".5">
          
        <LeftSlide></LeftSlide>
        </el-col>
        <el-col :span="12" >
          
           <MiddleInfo></MiddleInfo>
        </el-col>
        <el-col :span="7"  :pull=".5">

        <RightEdit></RightEdit>
        </el-col>
      </el-row>

</template>

<script>
    import LeftSlide from './left-slide/left-slide'
    import MiddleInfo from './middle-info/middle-info'
    import RightEdit from './right-edit/right-edit'
    export default {
        components: {
            LeftSlide,
            MiddleInfo,
            RightEdit
        }
    }
</script>
<style scoped>
    .edit-content {
        height: 90%;
    }
    
    .edit-content .el-col {
        height: 100%;
    }
</style>