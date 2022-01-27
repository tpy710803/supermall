<template>
      <div class="tab-bar-item" @click="itemClick">
        <div v-if="!isActive"><slot name="item-icon"></slot></div>
        <div v-else><slot name="item-icon-active"></slot></div>
        <div :style="activeStyle"><slot name="item-text"></slot></div>
        <!-- <img src="../../assets/img/tabbar/home.png" alt="">
        <div>首页</div> -->
      </div>
</template>

<script>
export default {
  name: 'TabBarItem',
  props:{
    path: String,
    activeColor:{
      type:String,
      default:'red'
    }
  },
  data(){
    return{
      // isActive: true

    }
  },
  computed:{
    isActive(){
      //使用方法是用path这个路径的值判断一下是不是等于-1等于-1的话就不是同一个路径，就不需要点击变颜色了
      return this.$route.path.indexOf(this.path) !==-1 
    },
    activeStyle(){
      return this.isActive ? {color:this.activeColor} : {}
    }
  },
  methods:{
    itemClick(){
      this.$router.replace(this.path)
    }
  }
}
</script>
<style>
  .tab-bar-item{
    flex: 1; /*水平下每一个元素之间的距离都相等*/ 
    text-align: center;
    height:49px;  /*普遍高度为49像素*/
    font-size: 14px;
  }
  .tab-bar-item img{
    width: 24px;
    height: 24px;
    margin-top: 3px;
    vertical-align: middle; /*去掉图片和文字之间的间隙*/ 
    margin-bottom: 2px;
  }
  /* .active{
    color:red;
  } */
</style>
