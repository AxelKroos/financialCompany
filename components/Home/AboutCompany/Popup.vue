<template>
  <div class="Popup" @click="clickPopup">
    <div class="Popup-images" @click="(e) => e.stopPropagation()">
      <div @click="dec" class="Popup-images--arrow---prev"><Arrow /></div>
      <img :src="require(`~/static/img/${items[selectedNum]}.jpeg`)" />
      <div @click="inc" class="Popup-images--arrow"><Arrow /></div>
    </div>

    <div class="Popup-arrows">
      <div @click="dec" class="prev"><Arrow /></div>
      <div @click="inc"><Arrow /></div>
    </div>
  </div>
</template>

<script>
import Arrow from "./Arrow";

export default {
  components: { Arrow },

  props: {
    clickPopup: {
      type: Function,
      default: () => {},
    },
  },

  data() {
    return {
      selectedNum: 0,
      items: ["svidetelstvo_1", "svidetelstvo_2"],
    };
  },

  computed: {
    getImage() {
      return "~static/img/about_company.webp";
    },
  },

  methods: {
    dec() {
      this.selectedNum =
        this.selectedNum === 0 ? this.items.length - 1 : this.selectedNum - 1;
    },

    inc() {
      this.selectedNum =
        this.selectedNum === this.items.length - 1 ? 0 : this.selectedNum + 1;
    },
  },
};
</script>

<style scoped lang="scss">
.Popup {
  $component: &;

  position: fixed;
  top: 0;
  width: 100%;
  bottom: 0;
  left: 0;
  right: 0;
  background: #00000087;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 10000;

  &-images {
    position: relative;
    width: 60%;
    height: 80%;
    max-width: 1020px;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 40px;
    padding: 40px;

    img {
      display: block;
      max-height: 100%;
      width: auto;
      height: auto;
    }

    &--arrow {
      display: block;

      &---prev {
        transform: rotate(180deg);
        position: relative;
        bottom: 4px;
      }
    }
  }

  &-arrows {
    display: none;

    .prev {
      transform: rotate(180deg);
      position: relative;
      bottom: 4px;
    }
  }

  svg {
    fill: white;
    cursor: pointer;
    transition: opacity 0.2s ease;

    &:hover {
      opacity: 0.6;
    }
  }

  @include mobile {
    &-images {
      &--arrow {
        display: none;

        &---prev {
          display: none;
        }
      }
    }

    &-arrows {
      display: flex;
      gap: 40px;
    }
  }
}
</style>