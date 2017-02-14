<template>
     <el-input v-model.trim="input" placeholder="请输入内容" size='small' @input.native='inputSync($event)'></el-input>  
</template>

<script>
    export default {

        data() {
            return {
                input: ''
            }
        },
        methods: {
            inputSync(e) {
                this.$emit('sync',this.input)
            }
        }
    }
</script>
<style scoped>

</style>