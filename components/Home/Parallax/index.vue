<template>
  <div class="Parallax">
    <div class="Parallax-overlay">
      <div class="Parallax-wrapper">
        <div class="Parallax-content">
          <h4>{{ title }}</h4>
          <div v-html="text"></div>
          <nuxt-link to="/">Подробнее</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "РАЗРЕШЕНИЕ СПОРОВ",
      text: `<p>Досудебное урегулирование споров Предоставление заключений о перспективах судебного разрешения спора Полный спектр услуг в области разрешения споров и судебной защиты интересов. </p>
      <p>Представление интересов клиента в национальных. Альтернативные методы разрешения споров (Alternative Dispute Resolution).Быстрое и эффективное исполнения судебных решений.</p>`,
    };
  },
};
</script>

<style scoped lang="scss">
.Parallax {
  background-image: url("~static/img/parallax.webp");
  background-attachment: fixed;
  background-origin: initial;
  background-clip: initial;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  &-overlay {
    background-color: rgba(0, 0, 0, 0.4);
  }

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    padding: 120px 0;
  }

  &-content {
    display: flex;
    flex-direction: column;
    gap: scaling(18);
    width: 50%;
    padding: 50px;
    background-color: rgba(18, 29, 52, 0.6);

    h4 {
      font-size: 22px;
      line-height: 25px;
      font-weight: 400;
    }

    div {
      line-height: 26px;
      font-weight: 300;
    }

    a {
      width: max-content;
      background-color: $c-blue-80;
      padding: scaling(10) scaling(36);
      color: $c-white-100;
      display: flex;
      gap: 15px;
      margin-top: scaling(18);
      transition: background-color 0.4s ease;

      &::after {
        content: "→";
      }

      &:hover {
        background-color: $c-blue-30;
      }
    }
  }

  @media (max-width: ($bp-tablet - 1)) {
    &-content {
      width: 90%;
      margin: 0 auto;
    }
  }
}
</style>