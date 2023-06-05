<template>
  <div class="ServiceDesc">
    <div class="ServiceDesc-wrapper">
      <div class="ServiceDesc-info">
        <div class="ServiceDesc-info--text">
          <h3>{{ title }}</h3>
          <p>{{ text }}</p>
        </div>

        <div class="ServiceDesc-info--link">Отправить заявку</div>
      </div>

      <div class="ServiceDesc-img"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Получите отличное обслуживание",
      text: "Создание структуры и комплексное сопровождение иностранного бизнеса и совместных предприятий Сопровождение сделок с иностранной недвижимостью Применении иностранных судебных решений Создание превентивной системы оценки рисков с трансграничными корпоративными отношениям Консультирование участников внешнеэкономической деятельности Налоговое планирование бизнес процессов и сделок для собственников, холдинговых и дочерних компаний Консультирование по вопросам международного налогообложения Комплексный анализ (tax due diligence) налоговой нагрузки и налоговых рисков трансграничных сделок Разработка стратегии защиты интересов налогоплательщика.  ",
    };
  },
};
</script>

<styles scoped lang="scss">
.ServiceDesc {
  $component: &;
  background-color: $c-gold-80;
  padding: 80px 20px;

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 0.6fr 0.4fr;
    gap: 30px;
  }

  &-info {
    display: flex;
    flex-direction: column;
    gap: 50px;

    &--text {
      display: flex;
      flex-direction: column;
      gap: 18px;
      color: $c-black-80;

      h3 {
        font-size: 27px;
        line-height: 30px;
        font-weight: 400;
      }
      h3 {
        font-size: 27px;
        line-height: 30px;
        font-weight: 400;
      }
    }

    &--link {
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
  }

  &-img {
    background-image: url('~static/img/serviceDesc.webp');
    background-size: cover;
    background-position: center;
  }

  @include mobile {
    &-wrapper {
      display: flex;
      flex-direction: column;
      gap: 30px;
    }

    &-img {
      width: 100%;
      height: 400px;
    }
  }
}
</styles>