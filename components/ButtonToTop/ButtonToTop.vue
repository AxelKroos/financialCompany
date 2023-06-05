<template>
  <div class="ButtonToTop" v-if="scrollPosition > 100" @click="scrollToTop">
    <div class="ButtonToTop-arrow" v-html="data"></div>
  </div>
</template>

<script>
import svg from "./svg";

export default {
  data() {
    return {
      data: svg.arrow,
      scrollPosition: 0,
    };
  },

  mounted() {
    window.addEventListener("scroll", () => {
      this.scrollPosition = window.scrollY;
    });
  },

  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
  },
};
</script>

<style scoped lang="scss">
.ButtonToTop {
  position: fixed;
  width: 40px;
  height: 40px;
  background-color: red;
  z-index: 1000;
  bottom: 22px;
  right: 20px;
  cursor: pointer;
  display: flex;

  &-arrow {
    width: max-content;
    height: max-content;
    margin: auto;
  }
}
</style>