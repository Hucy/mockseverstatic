<template>
    <div class="param-detail" :id='paramDetail.id'>

        <div class='basic-info-header' @click='showContent'>
            基本信息配置<span>路径,标签,描述,参数</span>
            <p class="change-info">
            <span>{{paramDetail.lastTime}}</span>
            <span>{{paramDetail.lastChangeUser}}</span>
            </p>
        </div>
        <div class ='basic-info-content' v-show='ifShow'>
                    <div class='top-header'>
            <div class="url" @click = 'nodeClick("url")' :class='currentEditNode=="url"?"active":""'>
                <p class="title"> 路径</p>
        <h1 >{{paramDetail.url}}</h1>
            </div>
            <div class="tag-list" @click = 'nodeClick("tag")' :class='currentEditNode=="tag"?"active":""'>
                <p class="title"> 标签</p>
                <div>
                     <el-tag v-for = 'tag in paramDetail.tagList' :key="tag" :type ='tag.type'>{{tag.name}}</el-tag>
            </div>
                </div>
           

        </div>
        
        <div  @click = 'nodeClick("des")' class="des" :class='currentEditNode=="des"?"active":""'>
        <p class="title"> 描述</p>
        <p>{{paramDetail.des}}</p>
        </div>
        
      
        <ul class='param-list' @click = 'nodeClick("param")' :class='currentEditNode=="param"?"active":""'>
            <li>
                <span>参数</span>
                <span>取值</span>
                <span>描述</span>
            </li>
            <li v-for = 'param in paramDetail.params'>
                <span>{{param.key}}</span>
                <span>{{param.value}}</span>
                <span>{{param.des}}</span>
            </li>
        </ul>
        
        </div>






    </div>        
</template>
<script>
    export default {
        props: ['paramDetail'],
        data() {
            return {
                currentEditNode: '',
                ifShow: false
            }
        },
        methods: {
            nodeClick(key) {
                // console.log(key)
                this.currentEditNode = key
                this.$emit('edit', key)
            },
            showContent() {
                this.ifShow = !this.ifShow
            }
        }
    }
</script>
<style scoped>
    p,
    h1 {
        padding: 4px;
        margin: 0;
    }
    
    .basic-info-header {
        box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, .12), 0px 0px 6px 0px rgba(0, 0, 0, .04);
        padding: 4px 8px;
        font-size: 20px;
        border: 1px solid #eaeefb;
        cursor: pointer;
        border-radius: 3px;
    }
    
    .basic-info-header span {
        font-size: 14px;
        color: #8492A6;
    }
    
    .basic-info-header span:first-child {
        margin-left: 20px;
    }
    
    .change-info span:first-child {
        margin-left: 0px;
    }
    
    .change-info span:last-child {
        margin-left: 5px;
        color: #1D8CE0;
    }
    
    .basic-info-content {
        background: #f9fafc;
        padding-top: 10px;
    }
    
    .top-header {
        display: flex;
        justify-content: space-between;
    }
    
    .url {
        width: 70%;
    }
    
    .tag-list {
        width: 29%;
    }
    
    .url,
    .tag-list,
    .des {
        cursor: pointer;
        border: 1px solid #eaeefb;
        border-top: 0;
        background: #fff;
    }
    
    .url:hover,
    .tag-list:hover,
    .des:hover,
    .param-list:hover,
    .active {
        box-shadow: 0 0 4px rgba(17, 205, 110, .6);
    }
    
    .el-tag {
        margin: 2px;
    }
    
    .des {
        font-size: 18px;
        margin: .5em 0;
    }
    
    .param-list {
        list-style: none;
        padding: 0;
        margin: .5em 0;
        cursor: pointer;
        background: #fff;
    }
    
    .param-list {
        font-size: 14px;
        color: #324057;
        text-align: center;
    }
    
    .param-list span {
        display: inline-block;
        height: 18px;
        line-height: 18px;
        border: 1px;
    }
    
    .param-list li:first-child {
        background-color: #eff2f7;
        border: 0;
    }
    
    .param-list li {
        border: 1px solid #eaeefb;
        border-top: 0;
        padding: 5px 0;
    }
    
    .param-list span:first-child {
        width: 20%;
    }
    
    .param-list span:nth-child(2) {
        width: 20%;
    }
    
    .param-list span:last-child {
        width: 50%;
    }
    
    .title {
        display: block;
        background-color: #eff2f7;
        border: 0;
        font-size: 14px;
        margin: 0;
        padding: 4px 8px;
    }
</style>