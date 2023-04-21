<template>
  <div class="Menu">
    <div class="Menu-logo">
      <img src="img/logo.png" />
    </div>

    <div class="Menu-pages">
      <div class="Menu-pages--desktop">
        <NuxtLink
          class="Menu-pages--desktopItem"
          v-for="(page, i) in pages"
          :key="`desktop_item-${i}`"
          :to="page.path"
        >
          {{ page.name }}
        </NuxtLink>
      </div>

      <div class="Menu-pages--mobile">
        <div
          class="burger"
          @click="toggleMenu"
          :class="isOpenMobile ? 'isActive' : ''"
        >
          <div class="burger-item"></div>
          <div class="burger-item"></div>
          <div class="burger-item"></div>
        </div>
      </div>
    </div>

    <div class="Menu-listMobile">
      <div class="wrapper" :class="isOpenMobile ? 'isActive' : ''">
        <NuxtLink
          class="Menu-listMobile--item"
          v-for="(page, i) in pages"
          :key="`mobile_item-${i}`"
          :to="page.path"
        >
          {{ page.name }}
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpenMobile: false,
      pages: [
        { name: "ГЛАВНАЯ", path: "/" },
        { name: "О КОМПАНИИ", path: "/about" },
        { name: "ПРОДУКТЫ", path: "/about" },
        { name: "АНАЛИТИКА", path: "/about" },
        { name: "КОРПОРАТИВНЫМ КЛИЕНТАМ", path: "/about" },
        { name: "КОНТАКТЫ", path: "/about" },
      ],
    };
  },

  methods: {
    toggleMenu() {
      this.isOpenMobile = !this.isOpenMobile;
    },
  },
};
</script>

<style lang="scss" scoped>
.Menu {
  $component: &;

  display: flex;
  align-items: center;
  padding: scaling(12) 0;
  position: sticky;
  top: 0;
  z-index: 1000;
  background-color: $c-blue-80;

  &-logo {
    width: scaling(350);
    padding: 0 0 0 scaling(20);
    margin: 0px;

    img {
      margin-left: scaling(90);
      height: scaling(60);
    }
  }

  &-pages {
    width: 100%;

    &--desktop {
      display: flex;
      align-items: center;
      gap: scaling(30);

      &Item {
        color: $c-white-100;
        font-size: scaling(14);
        transition: color $d-hover ease;

        &:hover {
          color: $c-gold-80;
        }
      }
    }

    &--mobile {
      display: none;
      .burger {
        display: flex;
        flex-direction: column;
        gap: 7px;

        &-item {
          width: 30px;
          height: 4px;
          background-color: $c-white-100;
          transform-origin: right;
          transition: transform 0.3s ease;
        }

        &.isActive {
          .burger-item {
            opacity: 0;
            &:first-child {
              opacity: 1;
              transform: rotate(315deg);
            }
            &:last-child {
              opacity: 1;
              transform: rotate(45deg);
            }
          }
        }
      }
    }
  }

  &-listMobile {
    position: absolute;
    top: 100%;
    width: 100%;
    height: max-content;
    transition: height .5s ease;
    display: none;

    .wrapper {
      width: 100%;
      height: 0vw;
      max-height: 30vw;
      display: flex;
      flex-direction: column;
      gap: 10px;
      background-color: $c-blue-80;
      transition: height 0.3s ease;
      overflow: scroll;

      .Menu-listMobile--item {
        padding: 10px 20px;
        color: $c-white-100;
        font-size: scaling(16);
      }

      &.isActive {
        height: 100vw;
      }
    }
  }

  @include mobile {
    justify-content: space-between;
    padding: 0;

    &-logo {
      width: max-content;
      padding: 20px;

      img {
        margin-left: 0;
      }
    }

    &-pages {
      width: max-content;
      display: flex;
      align-items: center;
      padding: 20px;

      &--desktop {
        display: none;
      }

      &--mobile {
        display: block;
      }
    }

    &-listMobile {
      display: block;
    }
  }
}
</style>