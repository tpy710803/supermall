<template>
    <div id="tab-bar">
        <slot></slot>
    </div>
</template>

<script>
export default {
  name: 'TabBar',
}
</script>
<style>
  #tab-bar{
    /*弹性布局，水平分布布局*/
    display: flex; 
    background-color: #f6f6f6;
    position:fixed;
    left: 0;
    right: 0;
    bottom: 0;
    box-shadow: 0 -1px 1px rgba(100, 100, 100, .2);  /*给组件加上阴影*/
  }

</style>
