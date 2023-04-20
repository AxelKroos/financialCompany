<template>
  <div class="HeaderContacts">
    <div class="HeaderContacts-block">
      <div
        v-for="(elem, i) in contacts"
        :key="i"
        class="HeaderContacts-block--item"
        v-text="elem"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      contacts: [
        "Тел. +7 (800) 123-4567",
        "info@afc.com",
        "111024, город Москва, улица Свердлова, дом 29, офис 2",
      ],
    };
  },
};
</script>


<style lang="scss" scoped>
.HeaderContacts {
  $component: &;

  font-size: scaling(14);

  &-block {
    display: flex;
    gap: scaling(10);

    &--item {
      &:not(:last-child) {
        &::after {
          content: "|";
          margin-left: scaling(10);
        }
      }
    }
  }
}
</style>