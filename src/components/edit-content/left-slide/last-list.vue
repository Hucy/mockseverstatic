<template>
    <div class = "last-list">
    <div class = 'filter-wrap'>

        <div class = 'tag-list'>
    <el-tag v-for = 'tag in tagList' :key="tag" :type ='tag.type' :closable = 'true' @close="handleClose(tag)">{{tag.name}}</el-tag>

        </div>


        <el-button type="primary" :icon="showType?'fa el-icon-fa-th-large':'fa el-icon-fa-th-list'" size = "small" @click="showListTypeHandle"></el-button>
    </div>
    <ul :class="showType?'type-block':'type-list'">
        
    </ul>
  </div>
</template>

<script>
    import ListItem from './list-item'

    export default {
        props: {
            tagList: Array,
            lastList: Array
        },
        data() {
            return {
                showType: true
            }
        },
        components: {
            ListItem
        },
        methods: {
            handleClose(tag) {
                this.$emit('tag-close', tag)
            },
            showListTypeHandle() {
                this.showType = !this.showType
            }
        }
    }
</script>
<style scoped>
    .filter-wrap .tag-list {
        width: 80%;
        display: inline-block;
        vertical-align: middle;
    }
    
    .filter-wrap .tag-list .el-tag {
        margin: 2px;
    }
    
    .filter-wrap .el-button {
        width: 15%;
        display: inline-block;
        vertical-align: middle;
    }
</style>