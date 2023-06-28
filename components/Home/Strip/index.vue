<template>
  <div class="Strip" :class="isLast ? 'isLast' : ''">
    <div class="Strip-wrapper">
      <div class="Strip-info">
        <h3>{{ title }}</h3>
        <p>{{ text }}</p>
      </div>
      <div class="Strip-button">Отправить заявку</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    isLast: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      title: "ПРАВО БЫТЬ УСПЕШНЫМ",
      text: "Коллектив нашей фирмы- это высококвалифицированные специалисты с опытом работы, постоянно повышающие свое профессиональное мастерство.",
    };
  },
};
</script>

<style scoped lang="scss">
.Strip {
  background-color: $c-gold-80;
  color: $c-black-80;
  padding: scaling(50);

  &.isLast {
    background-image: url("~static/img/background_1.webp");
    background-size: cover;
    background-position: center;
    color: $c-white-100;

    .Strip-button {
      border: 1px solid;
      border-color: #fbd5a9;
    }
  }

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    display: flex;
    align-items: center;
    gap: 20px;
  }

  &-info {
    width: 75%;

    h3 {
      font-size: 27px;
      line-height: 30px;
      font-weight: 400;
    }

    p {
      margin-top: 10px;
      line-height: 24px;
    }
  }

  &-button {
    width: 25%;
    width: max-content;
    background-color: $c-blue-80;
    padding: scaling(15) scaling(36);
    color: $c-white-100;
    display: flex;
    align-items: center;
    gap: 15px;
    height: max-content;
    cursor: pointer;
    transition: background-color 0.4s ease;

    &::after {
      content: "→";
    }

    &:hover {
      background-color: $c-blue-30;
    }
  }

  @media (max-width: ($bp-laptop - 1)) {
    &-wrapper {
      flex-direction: column;
      align-items: flex-end;
    }

    &-info {
      width: 100%;
    }

    &-button {
      padding: scaling(15) scaling(60);
    }
  }
}
</style>