<template>
      <div class="logo-wrap" @click = 'logoClickHandle'>
            <img src="../../../static/api.svg" alt="">
            <img src="../../../static/json.svg" alt="">
    </div>
</template>
<script>
  export default {
    methods: {
      logoClickHandle() {
        console.log(1);
      }
    }
  }
</script>
<style scoped>
      .logo-wrap {
        height: 100%;
       padding-top: 5%;
    }
    
    .logo-wrap img {
        height: 65%;
        display: inline-block;
        vertical-align: middle;
    }
</style>