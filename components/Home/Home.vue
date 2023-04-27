<template>
  <div class="Home">
    <Slider />
    <Advantages />
    <Directions />
    <AboutCompany />
    <Strip />
    <Services />
    <Parallax />
    <Causes />
  </div>
</template>

<script>
import Slider from "./Slider";
import Advantages from "./Advantages";
import Directions from "./Directions";
import AboutCompany from "./AboutCompany";
import Strip from "./Strip";
import Services from "./Services";
import Parallax from './Parallax';
import Causes from './Causes';

export default {
  components: {
    Slider,
    Advantages,
    Directions,
    AboutCompany,
    Strip,
    Services,
    Parallax,
    Causes,
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
  height: 10000px;
}
</style>