<template>
      
    <div class="right-edit">
        <el-row type='flex' align='top'>
            <el-col :span='15' > <TopFilter @filter='filterHandle'></TopFilter></el-col>
            <el-col :span='9'  > <HandleButton @save='saveHandle' @undo='undoHandle'></HandleButton></el-col>
        </el-row>    
        <EditComb edit-type="radio" edit-key="ss"></EditComb>
    </div>

</template>

<script>
    import TopFilter from './top-filter'
    import HandleButton from './handle-button'
    import EditComb from './edit-comb'

    export default {
        components: {
            TopFilter,
            HandleButton,
            EditComb
        },
        methods: {
            saveHandle() {
                console.log('save')
            },
            undoHandle() {
                console.log('undo')
            },
            filterHandle(item) {
                console.log(item);
            }
        }
    }
</script>
<style scoped>
    .right-edit {
        padding: 20px 0;
        height: 100%;
    }
</style>