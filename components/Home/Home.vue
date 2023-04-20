<template>
  <div class="Home">
    <Slider />
    <Advantages />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";

export default {
  components: {
    Slider,
    Advantages,
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: white;
}
</style>