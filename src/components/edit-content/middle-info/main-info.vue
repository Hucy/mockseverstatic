<template>
    <div class="main-info">
       <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick" :render-content='renderContent'
       :highlight-current='true'></el-tree>
    </div>      
</template>
<script>
    export default {
        data() {
            return {
                data: [{
                    label: '',
                    value: 'article',
                    children: [{
                        label: 'title',
                        value: 'article 路由'
                    }, {
                        label: 'description',
                        value: 'article 接口信息配置'
                    }, {
                        label: 'type',
                        value: 'object'
                    }, {
                        label: '',
                        value: 'properties',
                        children: [{
                            label: '',
                            value: 'code',
                            children: [{
                                label: 'title',
                                value: '返回代码'
                            }, {
                                label: 'description',
                                value: '服务器返回代码'
                            }, {
                                label: 'type',
                                value: 'integer'
                            }, {
                                label: 'minimum',
                                value: 0
                            }, {
                                label: 'maximum',
                                value: 10
                            }, ]
                        }]
                    }]
                }],
                defaultProps: {
                    children: 'children',
                    label: 'label'
                }
            };
        },
        methods: {
            handleNodeClick(data, node, content) {
                this.$emit('edit', node)

            },
            renderContent: function(h, node) {
                return h('span', {
                    "class": {
                        'node-label': true
                    }
                }, [h('i', node.data.label !== "" ? node.data.label + ":" : ""), h('i', node.data.value)])
            }
        }
    };
</script>
<style>
    .main-info {
        margin-top: 10px;
    }
    
    .main-info .el-tree {
        box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, .12), 0px 0px 6px 0px rgba(0, 0, 0, .04);
        border-radius: 3px;
    }
    
    .main-info .el-tree .node-label i:first-child {
        color: #475669
    }
    
    .main-info .el-tree .node-label i:last-child {
        font-style: normal;
    }
</style>