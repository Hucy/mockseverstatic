<template>
    <li>
        
    <el-card :body-style="{ padding: '0px' }" v-if="showType">
        <div class="tag-list">
            <el-tag v-for = 'tag in item.tagList' :key="tag" :type ='tag.type'>{{tag.name}}</el-tag>
        </div>
        
      <div style="padding: 4px 14px;">
        
        <p class = 'header'>
            {{item.url}}   
        </p>
        <p class = 'des'> {{item.des}}  </p>
        <ul class = 'paramsList'>
            <li>
                <span>参数</span>
                <span>取值</span>
                <span>描述</span>
            </li>
            <li v-for = 'param in item.params'>
                <span>{{param.key}}</span>
                <span>{{param.value}}</span>
                <span>{{param.des}}</span>
            </li>
        </ul>
        <div class="bottom ">
          <time class="time">{{item.lastTime}}</time>
          <span class="person">{{item.lastChangeUser}}</span>

          <div class = 'btn-list'>
               <el-button type="primary" size="mini" icon = 'fa el-icon-fa-clipboard'>复制</el-button>
               <el-button type="primary" size="mini" icon = 'fa  el-icon-fa-external-link'>打开</el-button>
                
         
          </div>
         
        </div>
      </div>
    </el-card>
    <div class='list-item' v-else>
        <p>{{item.url}}</p>
        <p>{{item.des}}</p>

    </div>


    </li>

</template>


<script>
    export default {
        props: {
            item: Object,
            showType: Boolean
        },



    }
</script>
<style scoped>
    .list-item {
        border: 1px solid #D3DCE6;
        overflow: hidden;
        border-radius: 4px;
    }
    
    .list-item p {
        margin: 0;
        padding: 4px 8px;
    }
    
    .el-card .header {
        margin: 0;
        padding: 0;
    }
    
    .el-card .tag-list {
        overflow: hidden;
    }
    
    .el-card .el-tag {
        margin: 2px;
        float: right;
    }
    
    .list-item p:first-child,
    .el-card .header {
        font-size: 20px;
        height: 20px;
        line-height: 20px;
    }
    
    .list-item p:last-child,
    .el-card .des {
        font-size: 16px;
        height: 20px;
        line-height: 20px;
        color: #8492A6;
    }
    
    .list-item,
    .el-card {
        margin: .1em 0;
        cursor: pointer;
        background: #fff;
    }
    
    .el-card .des {
        margin: 0;
        padding: 0;
    }
    
    .el-card .paramsList {
        list-style: none;
        padding: 0;
    }
    
    .el-card .paramsList {
        font-size: 14px;
        color: #324057;
        text-align: center;
    }
    
    .el-card .paramsList span {
        display: inline-block;
        height: 18px;
        line-height: 18px;
        border: 1px
    }
    
    .el-card .paramsList li:first-child {
        background-color: #eff2f7;
        border: 0;
    }
    
    .el-card .paramsList li {
        border: 1px solid #eaeefb;
        border-top: 0;
        padding: 5px 0;
    }
    
    .el-card .paramsList span:first-child {
        width: 20%;
    }
    
    .el-card .paramsList span:nth-child(2) {
        width: 20%;
    }
    
    .el-card .paramsList span:last-child {
        width: 50%;
    }
    
    .bottom {
        font-size: 12px;
        color: #8492A6;
        padding-top: 4px;
    }
    
    .btn-list {
        overflow: hidden;
        padding-top: 4px;
    }
    
    .btn-list button {
        float: right;
    }
    
    .btn-list button:first-child {
        margin-left: 5px;
    }
    
    .person {
        padding-left: 10px;
        color: #1D8CE0
    }
</style>