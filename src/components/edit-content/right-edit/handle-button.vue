<template>
      
    <div class="handle-btn">
      <el-button type="primary" icon="fa el-icon-fa-floppy-o" size="small" @click= 'saveHandle'>保存</el-button>
        <el-button type="primary" icon="fa el-icon-fa-undo" size="small" @click= 'undoHandle'>撤销</el-button>
    </div>

</template>

<script>
    export default {
        methods: {
            saveHandle() {
                this.$emit('save')
            },
            undoHandle() {
                this.$emit('undo')
            }
        }
    }
</script>
<style scoped>
    .handle-btn {
        text-align: right;
    }
</style>