<template>
  <div class="Causes">
    <div class="Causes-img"></div>
    <div class="Causes-info">
      <h3>{{ title }}</h3>
      <p>{{ text }}</p>

      <div class="Causes-info--block">
        <div
          class="Causes-info--blockItem"
          v-for="(item, i) in content"
          :key="`causes-${i}`"
        >
          <div class="Causes-info--blockItemSvg" v-html="item.svg"></div>
          <div class="Causes-info--blockItemText">
            <h4>{{ item.title }}</h4>
            <p>{{ item.text }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import svg from "./svg";
export default {
  data() {
    return {
      svg: svg,
      title: "ПОЧЕМУ ВЫБИРАЮТ НАС",
      text: "Наша команда четко видит и понимает коммерческую составляющую бизнеса и успешно справляется с комплексными проектами. ",
      content: [
        {
          svg: svg.svg1,
          title: "Опыт и практика",
          text: "Слаженная команда опытных специалистов. ",
        },
        {
          svg: svg.svg2,
          title: "Глубокая интеграция",
          text: "Глубоко интегрированных в бизнес-процессы. ",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.Causes {
  $component: &;

  display: grid;
  grid-template-columns: repeat(2, 1fr);

  &-img {
    background-image: url("~/static/img/causes.webp");
    background-position: center;
    background-size: cover;
  }

  &-info {
    background-color: $c-gold-80;
    color: $c-black-80;
    display: flex;
    flex-direction: column;
    gap: 18px;
    padding: 80px;

    h3 {
      font-size: 27px;
      line-height: 30px;
      font-weight: 400;

      &::after {
        content: "";
        width: 40px;
        height: 2px;
        background-color: $c-black-80;
        display: block;
        margin-top: 18px;
      }
    }

    &--block {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
      margin-top: scaling(55);

      &Item {
        display: flex;
        gap: 40px;

        &Text {
          display: flex;
          flex-direction: column;
          gap: 18px;

          h4 {
            font-size: 22px;
            line-height: 25px;
            font-weight: 400;
          }
        }
      }
    }
  }

  @include mobile {
    display: block;

    &-img {
      display: none;
    }

    &-info {
      padding: 80px 15px;

      &--block {
        display: flex;
        flex-direction: column;
        gap: 30px;

        &Item {
          gap: 20px;
        }
      }
    }
  }
}
</style>