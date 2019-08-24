<template>
  <div class="home">
    <Header></Header>
    <h1 class="hh">这是一个购物车的demo，你可以点击购物车按钮，进入购物车界面。</h1>
  </div>
</template>

<script>
import Header from "../components/Header";

export default {
  name: "home",
  components: {
    Header
  }
};
</script>

<style scoped>
.home > .hh {
  display: block;
  width: 100%;
  height: 200px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
</style>