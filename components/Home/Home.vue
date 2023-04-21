<template>
  <div class="Home">
    <Slider />
    <Advantages />
    <Directions />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";
import Directions from "./Directions";

export default {
  components: {
    Slider,
    Advantages,
    Directions
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
  height: 10000px;
}
</style>