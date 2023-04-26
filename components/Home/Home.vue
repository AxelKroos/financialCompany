<template>
  <div class="Home">
    <Slider />
    <Advantages />
    <Directions />
    <AboutCompany />
    <Strip />
    <Services />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";
import Directions from "./Directions";
import AboutCompany from "./AboutCompany";
import Strip from "./Strip";
import Services from "./Services";

export default {
  components: {
    Slider,
    Advantages,
    Directions,
    AboutCompany,
    Strip,
    Services,
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
  height: 10000px;
}
</style>