<template>
  <div class="goods">
      <goods-list-item v-for="item in goods" :goods-item="item "></goods-list-item>
  </div>
</template>

<script>
  import GoodsListItem from "./GoodsListItem";
  // 业务组件
  export default {
    name: "GoodList",
    components:{
      GoodsListItem
    },
    props:{
      goods:{
        type:Array,
        default(){
          return []
        }
      }
    }
  }
</script>

<style scoped>
.goods{
  display: flex;
  /*包裹*/
  flex-wrap: wrap;
  /*均等分*/
  /*justify-content:space-around ;*/
  justify-content:space-evenly ;
  /*padding: 2.5px;*/

  /*z-index: 1;*/
}
</style>
