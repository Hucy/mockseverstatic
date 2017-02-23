<template>
    <div class="edit-comb">
        <div class="node-handle">
           <span>{{editKey}}</span>
           <el-button type="warning" icon="fa el-icon-fa-trash-o" size="small" @click='removeNode'>移除</el-button>
        </div>
        <div class="edit-wrap">
        <TypeSync v-if='editType=="sync"' @sync='syncHandle'></TypeSync>
        <TypeRadio v-if='editType=="radio"' @radio='radioHandle'></TypeRadio>
        </div>
       
    </div>        
</template>

<script>
    import TypeSync from './sub-edit/type-sync'
    import TypeRadio from './sub-edit/type-radio'
    export default {
        props: ['editType','editKey'],
        components: {
            TypeSync,
            TypeRadio
        },
        methods: {
            syncHandle(value) {
                console.log(value)
            },
            radioHandle(value){
                console.log(value)
            },
            removeNode(){
                console.log('removeNode')
            }
        }
    }
</script>
<style scoped>
    .edit-comb {
        margin-top: .5em;
        background: #EFF2F7;
        border-radius: 3px;
        height: 97%;
    }
    .node-handle{
        box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, .1);
        padding: .5em;
    }
    .edit-wrap{
        padding: .5em;  
    }
    .node-handle span{
     font-size: 20px;
    color: #324057;
    display: inline-block;
    width:82%;
    }
</style>