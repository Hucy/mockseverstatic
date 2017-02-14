<template>
    <el-radio-group v-model="radio2" @change='radioChangeHandle'>
    <el-radio :label="'object'">Object</el-radio>
    <el-radio :label="'array'">Array</el-radio>
    <el-radio :label="'string'">String</el-radio>
    <el-radio :label="'integer'">integer</el-radio>
  </el-radio-group>
</template>
<script>
    export default {
    data () {
      return {
        radio2: 'object'
      };
    },
    methods:{
        radioChangeHandle(value){
            console.log(value)
        }
    }
  }
</script>
<style scoped>
    
</style>