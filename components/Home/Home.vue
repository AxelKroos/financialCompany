<template>
  <div class="Home">
    <Slider />
    <Advantages />
    <Directions />
    <AboutCompany />
    <Strip />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";
import Directions from "./Directions";
import AboutCompany from "./AboutCompany";
import Strip from "./Strip";

export default {
  components: {
    Slider,
    Advantages,
    Directions,
    AboutCompany,
    Strip,
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
  height: 10000px;
}
</style>