<template>
  <div class="Advantages">
    <div class="Advantages-wrapper">
      <div
        class="Advantages-item"
        v-for="(item, i) in content"
        :key="`advantage-${i}`"
      >
        <div class="Advantages-item--icon" v-html="item.svg"></div>

        <div class="Advantages-itemText">
          <h4 class="Advantages-itemText--title">{{ item.title }}</h4>
          <p class="Advantages-itemText--text">{{ item.text }}</p>
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
      data: svg,
      content: [
        {
          svg: svg.svg1,
          title: "Налоговая практика",
          text: "Налоговое планирование бизнес процессов и сделок для собственников, холдинговых и дочерних компаний. ",
        },
        {
          svg: svg.svg2,
          title: "Корпоративные решения",
          text: "Разработка оптимальной корпоративной модели управления Сопровождение инвестиционных фондов предприятий. ",
        },
        {
          svg: svg.svg3,
          title: "Быстрые решения",
          text: "Наша команда четко видит и понимает коммерческую составляющую бизнеса и быстро справляется с проектами. ",
        },
        {
          svg: svg.svg4,
          title: "Сопровождение сделок",
          text: "Полный цикл сопровождения сделок, проведение комплексной проверки (due diligence) объекта сделки. ",
        },
        {
          svg: svg.svg5,
          title: "Международная практика",
          text: "Создание превентивной системы оценки рисков с трансграничными корпоративными отношениям. ",
        },
        {
          svg: svg.svg6,
          title: "Консультирование",
          text: "Для достижения лучшего результата  вся работа должна быть сделана командой опытных специалистов. ",
        },
      ],
    };
  },
};
</script>


<styled lang="scss" scoped>
.Advantages {
  $component: &;

  padding: scaling(80) 0;
  background-image: url("~/static/img/Advantages.webp");
  background-size: cover;

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: scaling(20);
    padding: 0 20px;
  }

  &-item {
    display: flex;
    gap: scaling(30);

    &Text {
      display: flex;
      flex-direction: column;
      gap: 18px;

      &--title {
        font-size: scaling(22);
        line-height: scaling(25);
        font-weight: 400;
      }
    }
  }

  @include mobile {
    padding: 0;

    &-wrapper {
      gap: scaling(40);
    }

    &-item {
      flex-direction: column;
      gap: scaling(18);

      &Text {
        &--title {
          font-size: scaling(50);
          line-height: scaling(42);
        }

        &--text {
          font-weight: 300;
        }
      }
    }
  }
}
</styled>