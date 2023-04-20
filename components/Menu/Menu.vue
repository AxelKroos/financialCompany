<template>
  <div class="Menu">
    <div class="Menu-logo">
      <img src="img/logo.png" />
    </div>

    <div class="Menu-pages">
      <NuxtLink
        class="Menu-pages--item"
        v-for="(page, i) in pages"
        :key="i"
        :to="page.path"
      >
        {{ page.name }}
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
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
};
</script>

<style lang="scss" scoped>
.Menu {
  $component: &;

  display: flex;
  padding-bottom: scaling(12);
  position: sticky;
  top: 0;

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
    display: flex;
    align-items: center;
    gap: scaling(30);

    &--item {
      color: $c-white;
      font-size: scaling(14);
      transition: color $d-hover ease;

      &:hover {
        color: $c-gold-80;
      }
    }
  }
}
</style>