<template>
    <div class="left-slide">
        <TopSearch></TopSearch>
        <NewItem @click.native='newHandle'></NewItem>
        <LastList  :tag-list = 'tagList' :last-list="lastList" @tag-close = 'tagCloseHandle' @item-click='itemCilckHandle'></LastList>
    </div>
</template>

<script>
    import TopSearch from './top-search'
    import LastList from './last-list'
    import NewItem from './new-item'
    export default {
        components: {
            TopSearch,
            LastList,
            NewItem
        },
        data() {
            return {
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
                }],
                lastList: [{
                    id: "x1",
                    des: "xxx",
                    url: "xxx",
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: '',
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
                    }],
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '11'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '11'
                    }]
                }, {
                    id: "x2",
                    des: "xxx",
                    url: "xxx",
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: '12',
                    tagList: [{
                        key: 1,
                        type: "gray",
                        name: "标签一",
                    }, {
                        key: 2,
                        type: "success",
                        name: "标签",
                    }],
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '12'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '22'
                    }]
                }, {
                    id: "x2",
                    des: "xxx",
                    url: "xxx",
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: '12',
                    tagList: [{
                        key: 1,
                        type: "gray",
                        name: "标签一",
                    }, {
                        key: 2,
                        type: "success",
                        name: "标签",
                    }],
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '12'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '22'
                    }]
                }, {
                    id: "x2",
                    des: "xxx",
                    url: "xxx",
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: '12',
                    tagList: [{
                        key: 1,
                        type: "gray",
                        name: "标签一",
                    }, {
                        key: 2,
                        type: "success",
                        name: "标签",
                    }],
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '12'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '22'
                    }]
                }, {
                    id: "x2",
                    des: "xxx",
                    url: "xxx",
                    lastTime: '2016-12-14 14:36',
                    lastChangeUser: '12',
                    tagList: [{
                        key: 1,
                        type: "gray",
                        name: "标签一",
                    }, {
                        key: 2,
                        type: "success",
                        name: "标签",
                    }],
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: '12'
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: '22'
                    }]
                }]
            }
        },
        methods: {
            tagCloseHandle(tag) {
                this.tagList.splice(this.tagList.indexOf(tag), 1);
            },
            newHandle() {
                console.log('new')
            },
            itemCilckHandle(id) {
                console.log(id)
            }
        }
    }
</script>
<style scoped>
    .left-slide {
        height: 90%;
        padding-top: 10%;
    }
</style>