<template>
    <div class="left-slide">
        <TopSearch></TopSearch>
        <LastList  :tag-list = 'tagList' :last-list="lastList" @tag-close = 'tagCloseHandle'></LastList>
    </div>
</template>

<script>
    import TopSearch from './top-search'
    import LastList from './last-list'
    export default {
        components: {
            TopSearch,
            LastList
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
                    id: "1",
                    des: "xxx",
                    url: "xxx",
                    lastTime: 'ss',
                    lastChangeUser: '',
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: ''
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: ''
                    }]
                }, {
                    id: "1",
                    des: "xxx",
                    url: "xxx",
                    lastTime: 'ss',
                    lastChangeUser: '',
                    params: [{
                        key: 'xx',
                        value: "xx",
                        des: ''
                    }, {
                        key: 'xx',
                        value: "xx",
                        des: ''
                    }]
                }]
            }
        },
        methods: {
            tagCloseHandle(tag) {
                this.tagList.splice(this.tagList.indexOf(tag), 1);
            }
        }
    }
</script>
<style scoped>

</style>