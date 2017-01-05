<template>
     <el-input v-model.trim="input" placeholder="请输入内容" size='small' @input.native='input1($event)' @change.native='change1($event)'></el-input>  
</template>

<script>
    export default {

        data() {
            return {
                input: ''
            }
        },
        watch: {
            // input(newVal, oldVal) {
            //     this.$emit('sync', newVal)
            // }
        },
        methods: {
            input1(e) {
                console.log(e.target.value)
            },
            change1(e) {
                console.log(e.target.value)
            }
        }
    }
</script>
<style scoped>

</style>