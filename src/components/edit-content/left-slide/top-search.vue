<template>
    <el-input placeholder="请输入内容" v-model="searchText" style="" size="small">
    <el-button slot="append" icon="search" size="small"></el-button>
  </el-input>
</template>

<script>
    export default {
        data() {
            return {
                searchText: ''
            }
        },
        components: {

        }
    }
</script>
<style scoped>

</style>