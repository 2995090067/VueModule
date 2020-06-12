<template>
  <div>
    <!--    站位-->
<!--    <router-view></router-view>-->

    <tab-bar>
      <tab-bar-items :link=this.homelink>
        <img slot="item-icon" :src=this.homep>
        <img slot="item-icon-active" :src=this.homepl>
        <div slot="item-text">{{this.hometext}}</div>
      </tab-bar-items>

      <tab-bar-items :link=this.categorylink>
        <img slot="item-icon" :src=this.categoryp>
        <img slot="item-icon-active" :src=this.categorypl>
        <div slot="item-text">{{this.categorytext}}</div>
      </tab-bar-items>

      <tab-bar-items :link=this.cartlink>
        <img slot="item-icon" :src=this.cartp alt="">
        <img slot="item-icon-active" :src=this.cartpl alt="">
        <div slot="item-text">{{this.carttext}}</div>
      </tab-bar-items>

      <tab-bar-items :link=this.proflielink>
        <img slot="item-icon" :src=this.profilep>
        <img slot="item-icon-active" :src=this.profilepl>
        <div slot="item-text">{{this.profiletext}}</div>
      </tab-bar-items>
    </tab-bar>
  </div>
</template>

<script>
  import TabBarItems from "../../common/tabbar/module/TabBarItems";
  import TabBar from "../../common/tabbar/module/TabBar";
  export default {
    name: "MainTabBar",
    components:{
      // 注册组件
      TabBar,
      TabBarItems
    },
    data(){
      return{
        // 失去活跃已经获得活跃的路径
        homep:require("@/assets/img/tarbar/home.svg"),
        homepl:require("@/assets/img/tarbar/home_active.svg"),
        categoryp:require("@/assets/img/tarbar/category.svg"),
        categorypl:require("@/assets/img/tarbar/category_active.svg"),
        cartp:require("@/assets/img/tarbar/shopcart.svg"),
        cartpl:require("@/assets/img/tarbar/shopcart_active.svg"),
        profilep:require("@/assets/img/tarbar/profile.svg"),
        profilepl:require("@/assets/img/tarbar/profile_active.svg"),
        //对应组件的文字的名称
        hometext:'主页',
        categorytext:'分类',
        carttext:'购物车',
        profiletext:'我的',
        //对应跳转的组件的路径
        homelink:"/home",
        categorylink:"/category",
        cartlink:"/cart",
        proflielink:"/profile"
      }
    }
  }
</script>

<style scoped>

</style>
