<template>
  <div class="tabbars" @click="itemClick">
    <!--  tabbar      <img src="../../assets/img/tarbar/home.svg">-->
<!--    判断组件是否活跃-->
<!--    <slot v-if="!isActive" name="item-icon"></slot>-->
<!--    <slot v-else name="item-icon-active"></slot>-->
    <div v-if="!isActive">
      <slot name="item-icon"></slot>
<!--      插槽都包装一层，防止样式被之后的插槽替换-->
    </div>
    <div v-else>
      <slot name="item-icon-active"></slot>
    </div>
    <div :style="isActiveStyle ">
      <slot name="item-text"></slot>
    </div>

  </div>
</template>

<script>
  export default {
    name: "TabBarItems",
    props:{
      //父传子，父组件传过来消息,传的是父组件APP中的item的信息（当前场景）
      link:String,
      activeColor:{
        //这里接受父组件传来的颜色属性用来改变字体颜色
        type:String,
        default:'red'
      }
    },
    data(){
      return{
        // isActive: false
      }
    },
    methods:{
      itemClick(){
        this.$router.push(this.link).catch(e=>e)
        // this.isActive=! this.isActive
        // console.log("home:测试====》this.link");
      }
    },
    computed:{
      isActive(){
        //$route 处于活跃的组件
        //home-> item 1(/home)=true ,反之false
        return this.$route.path.indexOf(this.link) !==-1
      },
      isActiveStyle(){
        //动态绑定style，给字体
        return this.isActive?{color:this.activeColor}:{}
      }
    }
  }
</script>

<style scoped>
  .tabbars{
    text-align: center;
    flex: 1;
    /*ios,什么的tabbar一般是49px*/
    height: 49px;

    font-size: 14px;
  }
  .tabbars img{
    margin-top: 3px;
    /*图片的尺寸*/
    width: 24px;
    height:24px;
    /*去掉照片下面3px空间*/
    vertical-align: middle;
    margin-bottom: 2px;
  }
  /*.active{*/
  /*  color: #ff0059;*/
  /*}*/
</style>
