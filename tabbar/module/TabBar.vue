<template>
  <div id="tab-bar">
<!--    插槽-->
   <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "TabBar",
  }
</script>

<style scoped>
  /*动态引入初始化样式？*/
  /*@import "./assets/css/base.css";*/
  /*@import url("./assets/css/Base.css");*/
  #tab-bar{
    /*flex: auto;*/
    color: #282824;
    display: flex;
    background-color:#f6f6f6;

    position: fixed;
    left: 0;
    right: 0;
    bottom: 0;

    box-shadow: 0 -3px 1px rgba(100,100,100,.23);
  }

</style>