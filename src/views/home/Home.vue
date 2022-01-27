<template>
    <div id="home"> 
      <NavBar class="home-nav"><div slot="center">购物街</div></Navbar>
      <HomeSwiper :banners="banners"></HomeSwiper>
      <Recommend :Recommends="recommends"></Recommend>
      <Feature></Feature>
      <tabController :titles='tab_controller' class="tab-controller"></tabController>
        <ul>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
            <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
            <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
            <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>
          <li>列表一</li>

      </ul>
      <!-- <NavBar class="home-pop"><div slot="center">本周流行</div></NavBar> -->
    </div>
</template>
<script>
import NavBar from 'components/common/navbar/Navbar'
import HomeSwiper from './ChildCom/HomeSwiper'
import Recommend from  './ChildCom/Recommend'
import Feature from './ChildCom/Feature'
import tabController from 'components/content/TabController/tabController'
import {getHomeMultidata} from 'network/home.js'

export default {
  name: 'Home',
  components:{
     NavBar,
     HomeSwiper,
     Recommend,
     Feature,
     tabController
  },
  data(){
    return{
      banners:[],
      recommends:[],
      tab_controller : ['流行','新款','精选'],
      goods: {
        'pop': { page : 0,list : []},
        'news' : {page : 0,list : []},
        'sell' : {page : 0,list : []}
      }
    }
  },
  created(){
    //1.请求多个数据
    getHomeMultidata().then(res=>{
      this.banners = res.data.banner.list
      this.recommends = res.data.recommend.list
    })
  }
}
</script>
<style>
#home{
  padding-top: 44px;
}
.home-nav{
  background-color: var(--color-tint);
  font-weight: bold;
  color:white;
  position: fixed;
  left: 0;
  top: 0;
  right: 0;
  z-index: 9;
}
.home-pop{
  font-weight: bold;
}
.tab-controller{
  /*让导航栏锁住*/
  position: sticky;
  top: 44px;
}
</style>
