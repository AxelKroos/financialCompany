<template>
  <div class="Services">
    <div class="Services-wrapper">
      <div class="Services-head">
        <h3>{{ title }}</h3>
        <h4>{{ subtitle }}</h4>
      </div>

      <div class="Services-body">
        <div class="Services-bodyLeft">
          <div
            class="Services-bodyLeft--item"
            v-for="(item, i) in leftBlock"
            :key="`leftBlock-${i}`"
          >
            <div class="Services-bodyLeft--itemSvg" v-html="item.svg"></div>
            <div class="Services-bodyLeft--itemText">
              <h4>{{ item.title }}</h4>
              <p>{{ item.text }}</p>
            </div>
          </div>
        </div>
        <div class="Services-bodyRight">
          <h3>{{ rightBlock.title }}</h3>

          <ul>
            <li
              v-for="(item, i) in rightBlock.content"
              :key="`right_block-${i}`"
            >
              {{ item }}
            </li>
          </ul>
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
      title: "НАШИ СЕРВИСЫ",
      subtitle:
        "Это не только эксперты в области права, клиенты ценят наше глубокое понимание коммерческих аспектов ",
      leftBlock: [
        {
          svg: svg.svg1,
          title: "Разрешение споров Медиация",
          text: "Полный спектр услуг в области разрешения споров и судебной защиты интересов. ",
        },
        {
          svg: svg.svg2,
          title: "Сопровождение сделок",
          text: "Проведение комплексной проверки (due diligence) объекта сделки. ",
        },
        {
          svg: svg.svg3,
          title: "Корпоративные решения",
          text: "Разработка оптимальной корпоративной модели управления компанией. ",
        },
        {
          svg: svg.svg4,
          title: "Маркетинг и продвижение",
          text: "Сопровождение инвестиционных фондов, совместных предприятий. ",
        },
      ],
      rightBlock: {
        title: "Сопровождение сделок",
        content: [
          "Полный цикл сопровождения сделок  ",
          "Проведение комплексной проверки (due diligence) объекта сделки",
          "Консультирование в ходе переговорного процесса",
          "Структурирование сделки, подготовка документов по сделке (Letter of intent, Term sheet, NDA, SPA/SHA)",
          "Закрытие сделки. Согласование процедур после закрытия (post completion) сделки",
        ],
      },
    };
  },
};
</script>

<style scoped lang="scss">
.Services {
  $component: &;
  background-image: url("~static/img/background_1.webp");
  background-size: cover;
  background-position: center;

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    padding: scaling(80) 0;
    display: flex;
    flex-direction: column;
    gap: scaling(70);
  }

  &-head {
    width: 40%;
    margin: 0 auto;
    display: flex;
    flex-direction: column;
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

    h4 {
      font-size: 14px;
      font-weight: 300;
    }
  }

  &-body {
    display: grid;
    grid-template-columns: 2fr 1fr;
    gap: scaling(30);
    color: $c-black-80;
    padding: 0 20px;

    &Left {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: scaling(30);

      &--item {
        display: flex;
        gap: scaling(30);
        padding: 30px;
        background-color: $c-gold-80;

        &Text {
          display: flex;
          flex-direction: column;
          gap: scaling(18);

          h4 {
            font-size: 22px;
            line-height: 25px;
            font-weight: 400;
          }

          p {
            font-weight: 300;
          }
        }
      }
    }

    &Right {
      display: flex;
      flex-direction: column;
      gap: scaling(20);
      background-color: $c-gold-80;
      padding: 30px;

      h3 {
        font-size: 27px;
        line-height: 30px;
        font-weight: 400;
      }

      ul {
        margin-left: scaling(40);
      }
    }
  }

  @media (max-width: ($bp-tablet - 1)) {
    &-body {
      grid-template-columns: 1fr;
    }
  }

  @include mobile {
    &-bodyLeft {
      grid-template-columns: 1fr;
    }
  }
}
</style>