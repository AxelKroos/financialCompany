<template>
  <div class="Dots">
    <div
      class="Dots-circle"
      v-for="(circle, i) in content"
      :class="currentSlide === i ? 'isActive' : ''"
      :key="`circle-${i}`"
      @click="selectSlide(i)"
    ></div>
  </div>
</template>

<script>
export default {
  props: {
    content: {
      type: Array,
      default: [],
    },

    currentSlide: {
      type: Number,
      default: 0,
    },

    selectSlide: {
      type: Function,
      default: () => {},
    },
  },
};
</script>

<style lang="scss" scoped>
.Dots {
  $component: &;

  width: 100%;
  display: flex;
  justify-content: center;
  gap: scaling(10);
  position: absolute;
  bottom: 10%;

  &-circle {
    width: scaling(10);
    height: scaling(10);
    border-radius: 50%;
    background-color: $c-black-100;
    cursor: pointer;
    transition: background-color 0.2s ease;

    &:hover {
      background-color: $c-white-70;
    }

    &.isActive {
      background-color: $c-white-100;
    }
  }
}
</style>