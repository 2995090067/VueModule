<template>
  <div>
    <swiper>
      <swiper-item v-for="items in banners.list">
        <a :href="items.link">
          <img :src="items.image" alt="">
        </a>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
  import {getHomeMultidata} from "@/network/home";
  import {Swiper,SwiperItem} from "@/components/common/swiper/module"
  export default {
    name: "MySwiper",
    components:{
      Swiper,
      SwiperItem
    },
    data(){
      return{
        banners:[],
        recommends:[]
      }
    },
    created() {
      getHomeMultidata().then(res=>{
        this.banners=res.data.banner;
        // 由于接口更新，banner.list 里面才有书
        // console.log(this.banners);
        this.recommends=res.data.recommend;
      })
    }
  }
</script>

<style scoped>

</style>
