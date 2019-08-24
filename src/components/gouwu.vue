<template>
  <div class="index-wrap">
    <Header></Header>
    <lunbo :slides="slides"></lunbo>
    <zhanshi></zhanshi>
  </div>
</template>

<script>
import Header from "./Header"
import lunbo from './lunbo'
import zhanshi from "./zhanshi"
export default {
  components: {
    lunbo,
    Header,
    zhanshi
  },
  data () {
    return {
      slides: [
        {
          src: require('../assets/img/l2.jpg'),
          title: 'xxx1',
        },
        {
          src: require('../assets/img/l3.jpg'),
          title: 'xxx2',
        },
        {
          src: require('../assets/img/l4.jpg'),
          title: 'xxx3',
        }
      ]
    }
  }
}
</script>

<style scoped>
  .index-wrap {
    overflow: hidden;
}
</style>
