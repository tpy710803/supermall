<template>
    <div class="tab-controller">
      <div v-for="(item,index) in titles" :class="{active:index===currentIndex}"  @click="tabClick(index)"
        class="tab_controller_item"> 
        <span>{{item}}</span>
      </div>
    </div>
</template>
<script>
export default {
  name: 'tabController',
  props:{
    titles:{
      type:Array,
      default(){
        return []
      }
    }
  },
  data(){
    return{
        currentIndex : 0 
    }
  },
  methods:{
    tabClick(index){
      this.currentIndex = index
    }
  },
  components :{
  }
}
</script>
<style>
.tab-controller{
  display: flex;
  text-align: center;
  line-height: 40px;
  height: 40px;
  font-size: 15px;
  background-color: #fff;
}
.tab_controller_item{
  flex: 1;
}
.active{
  color:var(--color-high-text);
  
}
.active span{
  border-bottom: 3px solid var(--color-tint);
}
.tab_controller_item span{
  padding: 3px;
}
</style>
