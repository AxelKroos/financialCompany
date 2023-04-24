<template>
  <div class="Home">
    <Slider />
    <Advantages />
    <Directions />
    <AboutCompany />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";
import Directions from "./Directions";
import AboutCompany from './AboutCompany';

export default {
  components: {
    Slider,
    Advantages,
    Directions,
    AboutCompany
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
  height: 10000px;
}
</style>