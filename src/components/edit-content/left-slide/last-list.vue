<template>
    <div class = "last-list">
    <div class = 'filter-wrap'>

        <div class = 'tag-list'>
    <el-tag v-for = 'tag in tagList' :key="tag" :type ='tag.type' :closable = 'true' @close="handleClose(tag)">{{tag.name}}</el-tag>

        </div>


        <el-button type="primary" :icon="showType?'fa el-icon-fa-th-large':'fa el-icon-fa-th-list'" size = "small" @click="showListTypeHandle"></el-button>
    </div>
    <ul :class="showType?'type-block':'type-list'" class="last-list-wrap">
        <ListItem v-for ='item in lastList ' :item = 'item' :show-type =' showType' :ref ="item.id" @click.native = 'itemHandle(item.id)'></ListItem>
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
            },
            itemHandle(id) {
                this.$emit('item-click', id)
            }
        }
    }
</script>
<style scoped>
    .last-list {
        height: 100%;
    }
    
    .filter-wrap {
        margin: 1em 0;
        background: #EFF2F7;
        height: 9%;
        padding: .2em;
        border-radius: 4px;
        margin-bottom: -0.1em;
    }
    
    .filter-wrap .tag-list {
        width: 82%;
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
    
    .last-list-wrap {
        padding: 0;
        margin: 0;
        background: #EFF2F7;
        padding: 4px;
        border-radius: 4px;
        height: 88%;
        overflow-x: hidden;
        overflow-y: auto;
    }
    /* 设置滚动条的样式 */
    
    .last-list-wrap::-webkit-scrollbar {
        width: 4px;
    }
    
    .last-list-wrap::-webkit-scrollbar-thumb {
        border-radius: 10px;
        background: rgba(0, 0, 0, 0.1);
    }
    
    .type-list li {
        list-style: none;
    }
</style>