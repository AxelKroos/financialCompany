<template>
  <div class="Arrows">
    <div class="Arrows-content">
      <div class="prev" @click="throttle(prevSlide, 200)">
        <Arrow />
      </div>

      <div class="next" @click="throttle(nextSlide, 200)">
        <Arrow />
      </div>
    </div>
  </div>
</template>
<script>
import Arrow from "./Arrow";

export default {
  components: { Arrow },

  props: {
    prevSlide: {
      type: Function,
      default: () => {}
    },

    nextSlide: {
      type: Function,
      default: () => {}
    }
  },

  data() {
    return {
      isThrottled: false,
    };
  },

  methods: {
    throttle(fn, timeout) {
      if (this.isThrottled) return;
      this.isThrottled = true;
      fn();
      setTimeout(() => {
        this.isThrottled = false;
      }, timeout);
    }
  },
};
</script>

<style lang="scss" scoped>
.Arrows {
  position: absolute;
  top: 47%;
  width: 100%;
  display: flex;
  justify-content: center;

  &-content {
    width: 90%;
    display: flex;
    justify-content: space-between;

    .prev,
    .next {
      fill: $c-white;
      cursor: pointer;
      transition: opacity 0.2s ease;

      &:hover {
        opacity: 0.7;
      }
    }
    .prev {
      transform: rotate(180deg);
    }
  }
}
</style>
