<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles"
         class="tab-control-item"
         :class="{active:currentIndex===index}"
         @click="tabClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "TabControl",
    data(){
      return {
        currentIndex:0
      }
    }
    ,
    props: {
      titles: {
        type: Array,
        default() {
          return []
        }
      }
    },
    methods:{
      tabClick(index){
        this.currentIndex=index;
        // 内部传外部自定义事件
        this.$emit('tabType',index)
      }
    }
  }
</script>

<style scoped>
  .tab-control{
    display: flex;
    text-align: center;

    height: 40px;
    line-height: 40px;
    font-size: 15px;

    background-color: #fff;
  }
  .tab-control-item{
    flex: 1;
  }
  .tab-control-item span{
    padding: 5px;
  }
  .active{
    /*高亮*/
    color: var(--color-high-text);
  }
  .active span{
    border-bottom: 2px solid var(--color-high-text);
  }
</style>
