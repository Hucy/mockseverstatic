<template>    
    <div class = 'middle-info'>
        <ParamDetail :param-detail='paramDetail' @edit = 'editParamHandle'></ParamDetail>
        <MainInfo :main-info='mainInfo' @edit = 'editTreeNodeHandle' ></MainInfo>  
    </div>
</template>

<script>
    import MainInfo from './main-info'
    import ParamDetail from './param-detail'
    export default {
        data() {
            return {
                mainInfo: {
                    "article": {
                        "title": "article 路由",
                        "description": "article 接口信息配置",
                        "type": "object",
                        "properties": {
                            "code": {
                                "title": "返回代码",
                                "description": "服务器返回代码",
                                "type": "integer",
                                "minimum": 0,
                                "maximum": 10,
                                "exclusiveMinimum": true
                            },
                            "message": {
                                "title": "返回信息",
                                "description": "服务器返回信息",
                                "type": "string",
                                "chance": {
                                    "sentence": {
                                        "words": 5
                                    }
                                }
                            },
                            "articlelist": {
                                "title": "文章列表",
                                "description": "文章列表",
                                "type": "array",
                                "minItems": 10,
                                "items": {

                                    "name": {
                                        "title": "文章名称",
                                        "description": "文章名称",
                                        "type": "string",
                                        "chance": {
                                            "sentence": {
                                                "words": 5
                                            }
                                        }
                                    },
                                    "time": {
                                        "title": "出版时间",
                                        "description": "出版时间",
                                        "type": "string",
                                        "chance": {
                                            "date": {
                                                "string": true,
                                                "american": false
                                            }
                                        }
                                    }
                                }
                            }

                        },
                        "required": ["articlelist", "code", "message"]
                    }
                },
                paramDetail: {
                    id: 'x1',
                    url: 'xxx',
                    des: 'xxx',
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: 'uanhsksh',
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '11'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '11'
                    }],
                    tagList: [{
                        key: 1,
                        type: "gray",
                        name: "标签一",
                    }, {
                        key: 2,
                        type: "success",
                        name: "标签",
                    }, {
                        key: 3,
                        type: "success",
                        name: "标签",
                    }, {
                        key: 4,
                        type: "success",
                        name: "标签",
                    }, {
                        key: 5,
                        type: "success",
                        name: "标签",
                    }]

                },

            }
        },
        components: {
            MainInfo,
            ParamDetail
        },
        methods: {
            editParamHandle(key) {
                console.log(key)
            },
            editInfoHandle(key) {
                console.log(key)
            },
            editTreeNodeHandle(node) {
                console.log(node)
            }
        }
    }
</script>
<style scoped>
    .middle-info {
        padding: 20px 30px;
    }
</style>