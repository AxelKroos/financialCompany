<template>
  <div class="Home" id="home">
    <Slider />
    <AboutCompany :anchor="'company'"/>
    <DefaultBlock :text="'Банковские гарантии'" :anchor="'guarantees'"/>
    <DefaultBlock :text="'Кредиты'" :anchor="'credits'"/>
    <DefaultBlock :text="'Наши проекты'" :anchor="'projects'"/>
    <Contacts :anchor="'contacts'"/>
    <!-- <Advantages />
    <Directions />
    <AboutCompany />
    <Strip />
    <Services />
    <Parallax />
    <Causes />
    <Strip :isLast="true" />
    <ServiceDesc />
    <Statistics /> -->
  </div>
</template>

<script>
import Slider from "./Slider";
import DefaultBlock from "./DefaultBlock";
// import Advantages from "./Advantages";
// import Directions from "./Directions";
import AboutCompany from "./AboutCompany";
// import Strip from "./Strip";
// import Services from "./Services";
// import Parallax from "./Parallax";
// import Causes from "./Causes";
// import ServiceDesc from "./ServiceDesc";
// import Statistics from "./Statistics";
import Contacts from "./Contacts";

export default {
  components: {
    Slider,
    DefaultBlock,
    // Advantages,
    // Directions,
    AboutCompany,
    // Strip,
    // Services,
    // Parallax,
    // Causes,
    // ServiceDesc,
    // Statistics,
    Contacts
  },
};
</script>

<style scoped lang="scss">
.Home {
  color: $c-white-100;
}
</style>