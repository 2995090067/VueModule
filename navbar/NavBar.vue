<template>
  <div class="nav-bar">
<!--    //导航-->
    <div class="left"><slot name="left"></slot></div>
    <div class="centers"><slot name="centers"></slot></div>
    <div class="right"><slot name="right"></slot></div>
  </div>
</template>

<script>
  export default {
    name: "NavBar"
  }
</script>

<style scoped>
  .nav-bar{
    display: flex;
    height: 44px;
    line-height: 44px;
    /*如果有什么状态栏就再加20*/
    text-align: center;
    box-shadow: 0 1px 1px rgba(100, 100, 100, 0.48);
  }
  .right,.left{
    width: 60px;
  }
  .centers{
    flex: 1;
  }

</style>
