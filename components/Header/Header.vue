<template>
  <div class="Header">
    <div class="Header-content">
      <HeaderContacts />
    </div>
  </div>
</template>

<script>
</script>

<style lang="scss" scoped>
.Header {
  $component: &;

  display: flex;

  &-content {
    width: 100%;
    max-width: $w-1170;
    margin: auto;
    display: flex;
    justify-content: space-between;
    color: $c-gray-80;
    padding: scaling(20) scaling(25);

    @include mobile {
      display: none;
    }
  }
}
</style>
