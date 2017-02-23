<template>
  <div class="type-radio"> 
  <el-radio-group v-model="radio2" @change='radioChangeHandle'>
    <el-radio :label="'object'">Object</el-radio>
    <el-radio :label="'array'">Array</el-radio>
    <el-radio :label="'string'">String</el-radio>
    <el-radio :label="'integer'">integer</el-radio>
  </el-radio-group>
      <div class="constraint-wrap">
        <p>约束条件：</p>
        <div class="optional-list">
          <p>可选：</p>
          <el-tag v-for = ' optional in optionalList' @click.native.stop
 ='addOptionHandle(optional)' >{{optional}} <i class="el-icon-plus"></i></el-tag>
        </div>
        <div class="selected-list">
           <p>已选：</p>
          <el-tag v-for = '(optional,key) in choosedList'  closable='true' @close ='removeOptionHandle(key)' >{{optional}}</el-tag>
        </div>
      </div>
    </div>
</template>
<script>
    export default {
    data () {
      return {
        radio2: 'object',
        constraintList:{
          object:[11,21,31,12,212232],
          array:[1,2,3],
          string:[1,2,3],
          integer:[1,2,3]
        },
        choosedList:[11,21]
      };
    },
    computed:{
      optionalList(){
        let arr = this.constraintList[this.radio2].slice()
        this.choosedList.forEach((i)=>{
            arr.splice(arr.indexOf(i),1)
        })
        return arr
      }
    },
    methods:{
        radioChangeHandle(value){
           this.choosedList=[]
        },
        addOptionHandle(optional){
          this.choosedList.push(optional)
        },
        removeOptionHandle(key){
          this.choosedList.splice(key,1)
        }
       
    }
  }
</script>
<style scoped>
  .el-tag{    margin: 2px;}
    .el-icon-plus{
    border-radius: 50%;
    text-align: center;
    position: relative;
    cursor: pointer;
    font-size: 12px;
    transform: scale(.75, .75);
    height: 18px;
    width: 18px;
    line-height: 18px;
    vertical-align: middle;
    top: -1px;
    right: -2px;
    }
    .el-icon-plus:hover {
    background-color: #fff;
    color: #8492a6;
}
</style>