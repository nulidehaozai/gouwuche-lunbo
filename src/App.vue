<template>
  <div id="app">
    
    <div id="nav">
      <router-link to="/">介绍界面</router-link> |
      <router-link to="/about">购物车</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {

}
</script>

<style>
@import "./assets/css/base.css";
#nav{
  width: 100%;
  text-align: center;
  background-color: pink;
  position: fixed;
  bottom: 0;
  left: 0;
  height: 36px;
  color: white;
  text-align: center;
  line-height: 36px;
}
</style>

