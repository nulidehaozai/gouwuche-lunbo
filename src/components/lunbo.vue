<template>
<!--轮播图部分-->
  <div class="slide-show" @mouseover="clearInv" @mouseout="runInv">
    <div class="slide-img">
      <a :href="slides[nowIndex].href">
        <transition name="slide-trans">
          <img v-if="isShow" :src="slides[nowIndex].src" />
        </transition>
        <transition name="slide-trans-old">
          <img v-if="!isShow" :src="slides[nowIndex].src" />
        </transition>
      </a>
    </div>
    <h2>{{ slides[nowIndex].title }}</h2>
    <ul class="slide-pages">
      <li @click="goto(prevIndex)">&lt;</li>
      <li v-for="(item, index) in slides" :key="index" @click="goto(index)">
        <a :class="{on: index === nowIndex}">{{ index + 1 }}</a>
      </li>
      <li @click="goto(nextIndex)">&gt;</li>
    </ul>
  </div>
  <!--展示区部分-->
</template>

<script>
export default {
  props: {
    slides: {
      type: Array,
      default: function() {
        return [];
      }
    },
    inv: {
      type: Number,
      default: 2000
    }
  },
  data() {
    return {
      nowIndex: 0,
      isShow: true
    };
  },
  computed: {
    prevIndex() {
      if (this.nowIndex === 0) {
        return this.slides.length - 1;
      } else {
        return this.nowIndex - 1;
      }
    },
    nextIndex() {
      if (this.nowIndex === this.slides.length - 1) {
        return 0;
      } else {
        return this.nowIndex + 1;
      }
    }
  },
  methods: {
    goto(index) {
      this.isShow = false;
      setTimeout(() => {
        this.isShow = true;
        this.nowIndex = index;
      }, 10);
    },
    runInv() {
      this.invId = setInterval(() => {
        this.goto(this.nextIndex);
      }, this.inv);
    },
    clearInv() {
      clearInterval(this.invId);
    }
  },
  mounted() {
    this.runInv();
  }
};
</script>

<style scoped>
.slide-trans-enter-active {
  transition: all 0.5s;
}
.slide-trans-enter {
  transform: translateX(100%);
}
.slide-trans-old-leave-active {
  transition: all 0.5s;
  transform: translateX(-100%);
}
.slide-show {
  position: relative;
  margin: 30px auto;
  width: 100%;
  height: 200px;
  overflow: hidden;
}
.slide-show h2 {
  position: absolute;
  width: 100%;
  color: #fff;
  background: #000;
  opacity: 0.5;
  bottom: 0;
  margin: 0;
  height: 32px;
  padding-left: 15px;
}
.slide-img {
  width: 100%;
}
.slide-img img {
  width: 100%;
  height: 100%;
  position: absolute;
  top: 0;
}
.slide-pages {
  position: absolute;
  bottom: 0;
  margin-bottom: 5px;
  right: 15px;
}
.slide-pages li {
  display: inline-block;
  padding: 0 10px;
  cursor: pointer;
  color: #fff;
  font-size: 16px;
}
.slide-pages li .on {
  color: deeppink;
  text-decoration: underline;
}
</style>
