<template>
  <div class="AboutCompany" :id="anchor">
    <div class="AboutCompany-wrapper">
      <div class="AboutCompany-title">
        <h3>{{ title }}</h3>
        <p v-html="subtitle"></p>
      </div>

      <div class="AboutCompany-content">
        <div class="AboutCompany-content--item">
          <img src="~static/img/about_company.webp" />
        </div>
        <div class="AboutCompany-content--item">
          <h4>{{ content.title }}</h4>
          <p>{{ content.text }}</p>
          <div class="link" @click="clickPopup">Узнать подробнее</div>
        </div>
      </div>
    </div>

    <Popup v-if="isOpenPopup" :clickPopup="clickPopup" />
  </div>
</template>

<script>
import Popup from "./Popup.vue";

export default {
  props: {
    anchor: {
      type: String,
      required: true,
    },
  },

  components: {
    Popup,
  },

  data() {
    return {
      title: "О КОМПАНИИ",
      subtitle:
        "ООО «Финансовая компания РусФин» - динамично развивающаяся компания. <br /> Учреждена в 2012 году топ-менеджерами банков и крупнейшего ритейлера РФ.",
      content: {
        title: "НАША ГАРАНТИЯ",
        text: "Клиентами нашей компании «Русфин» становятся как фирмы малого бизнеса, так и крупные организации, имеющие филиалы по всей стране. Поверив в нас однажды, наши Клиенты обращаются к нам на постоянной основе и рекомендуют своим партнерам как проверенную и надежную компанию, помогающую срочно получить банковскую гарантию по госконтракту, банковскую таможенную гарантию, оказывающую услуги тендерного кредитования.",
      },
      isOpenPopup: false
    };
  },

  methods: {
    clickPopup() {
      this.isOpenPopup = !this.isOpenPopup
    }
  }
};
</script>

<style scoped lang="scss">
.AboutCompany {
  $component: &;

  background-image: url("~/static/img/background_1.webp");
  background-size: cover;
  padding: scaling(80) 0;

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
  }

  &-title {
    width: 100%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: scaling(18);
    text-align: center;

    h3 {
      font-size: 27px;
      line-height: 30px;
      font-weight: 400;

      &::after {
        content: "";
        width: 40px;
        height: 2px;
        background-color: $c-white-100;
        display: block;
        margin: 0 auto;
        margin-top: 18px;
      }
    }
  }

  &-content {
    display: flex;
    gap: scaling(30);
    margin: scaling(70) scaling(20) 0 scaling(20);

    &--item {
      color: $c-black-100;

      &:first-child {
        width: 70%;

        img {
          width: 100%;
        }
      }

      &:last-child {
        width: 30%;
        background-color: $c-gold-80;
        padding: 40px;

        h4 {
          font-size: 22px;
          line-height: 25px;
          font-weight: 400;

          &::after {
            content: "";
            width: 40px;
            height: 2px;
            background-color: $c-black-100;
            display: block;
            margin-top: 18px;
          }
        }

        p {
          margin-top: 15px;
          line-height: 24px;
          font-weight: 300;
        }
      }

      .link {
        width: max-content;
        background-color: $c-blue-80;
        padding: scaling(10) scaling(36);
        color: $c-white-100;
        display: flex;
        gap: 15px;
        margin-top: scaling(30);
        transition: background-color 0.4s ease;
        cursor: pointer;

        &::after {
          content: "→";
        }

        &:hover {
          background-color: $c-blue-30;
        }
      }
    }
  }

  @media (max-width: ($bp-laptop - 1)) {
    &-content {
      flex-direction: column;
      gap: 0;

      &--item {
        &:first-child {
          width: 100%;
        }

        &:last-child {
          width: 100%;
        }
      }
    }
  }
}
</style>