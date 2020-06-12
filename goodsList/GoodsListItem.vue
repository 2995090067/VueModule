<template>
  <div class="goodsItem">
    <img :src="goodsItem.show.img">
    <div class="goods-info">
      <p>{{goodsItem.title}}</p>
      <span class="price">{{goodsItem.price}}</span>
      <span class="collect">{{goodsItem.cfav}}</span>
    </div>
  </div>
</template>

<script>
  export default {
    name: "GoodsListItem"
    ,
    props:{
      goodsItem:{
        type:Object,
        default(){
          return {}
        }
      }
    }
  }
</script>

<style scoped>
  /*子绝父相*/
  .goodsItem{
    padding-bottom: 40px;
    /*相对布局*/
    position: relative;
    /*warp*/
    width: 48%;
  }
  .goodsItem img{
    width: 100%;
    border-radius: 5px;

    /*这里会造成图片拉升的效果，但是图片大小都不一样，暂时不管了*/
    height: 100%;
  }
  /*绝对定位*/
  .goods-info{
    font-size: 12px;
    position: absolute;
    bottom: 5px;
    left: 0;
    right: 0;
    overflow: hidden;
    text-align: center;
  }
  .goods-info p{
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-bottom: 3px;
  }
  .goods-info .price {
    color: var(--color-high-text);
    margin-right: 20px;
  }
  .goods-info .collect {
    position: relative;
  }
  /*伪元素*/
  /*css中的一些伪类，就像我们常用到的a:hover*/
  .goods-info .collect::before {
    content: '';
    position: absolute;
    left: -15px;
    top: -1px;
    width: 14px;
    height: 14px;
    background: url("~@/assets/img/common/collect.svg") 0 0/14px 14px;
  }
</style>
