<template>
    <div class="main-info">
       <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick"></el-tree>
    </div>      
</template>
<script>
    export default {
        data() {
            return {
                data: [{
                    label: '一级 2',
                    children: [{
                        label: '二级 2-1',
                        children: [{
                            label: '二级 2-1',
                            children: [{
                                label: '二级 2-1',
                                children: [{
                                    label: '二级 2-1'
                                }, {
                                    label: '二级 2-2'
                                }]
                            }, {
                                label: '二级 2-2'
                            }]
                        }, {
                            label: '二级 2-2'
                        }]
                    }, {
                        label: '二级 2-2'
                    }]
                }],
                defaultProps: {
                    children: 'children',
                    label: 'label'
                }
            };
        },
        methods: {
            handleNodeClick(data) {
                console.log(data);
            }
        }
    };
</script>
<style scoped>
    .main-info {
        margin-top: 10px;
    }
    
    .el-tree {
        box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, .12), 0px 0px 6px 0px rgba(0, 0, 0, .04);
        border-radius: 3px;
    }
</style>