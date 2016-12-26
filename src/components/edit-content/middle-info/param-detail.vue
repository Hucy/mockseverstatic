<template>
    <div class="param-detail" :id='paramDetail.id'>
        <h1 class="url">{{paramDetail.url}}</h1>
        <div class="tag-list">
            <el-tag v-for = 'tag in paramDetail.tagList' :key="tag" :type ='tag.type'>{{tag.name}}</el-tag>
        </div>
        <p>{{paramDetail.des}}</p>
        <ul class='param-list'>
            <li v-for = 'param in paramDetail.params'>
                <span>{{param.key}}</span>
                <span>{{param.value}}</span>
                <span>{{param.des}}</span>
            </li>
        </ul>
        <p class="bottom-info">
            <span>{{paramDetail.lastTime}}</span>
            <span>{{paramDetail.lastChangeUser}}</span>
        </p>
    </div>        
</template>
<script>
    export default {
        props: ['paramDetail'],
        data() {
            return {

            }
        }
    }
</script>
<style>

</style>