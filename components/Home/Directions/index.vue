<template>
  <div class="Directions">
    <div class="Directions-content">
      <div class="Directions-content--item"></div>
      <div class="Directions-content--item">
        <h3 class="title">{{ title }}</h3>
        <div class="line"></div>
        <div class="text">{{ text }}</div>
        <div class="list">
          <li class="listItem" v-for="(item, i) in list" :key="`listItem-${i}`">
            {{ item }}
          </li>
        </div>
        <NuxtLink class="link" :to="'/'"> Подробнее </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "ОСНОВНЫЕ НАПРАВЛЕНИЯ",
      text: "Среди наших клиентов, Российские и международные фонды прямых инвестиций, собственники динамично развивающихся частных бизнесов с растущей капитализацией и подразделения многоотраслевых холдингов.",
      list: [
        "Налоговое консультирование.",
        "Разрешение споров. Медиация.",
        "Банкротство.",
        "Сопровождение сделок",
        "Корпоративные решения",
        "Налоговая практика",
      ],
    };
  },
};
</script>

<style scoped lang="scss">
.Directions {
  $component: &;

  &-content {
    display: flex;

    &--item {
      width: 100%;

      &:first-child {
        background-image: url("~/static/img/directions.webp");
        background-size: cover;
        background-position: center;
      }

      &:last-child {
        padding: scaling(80);
        background-color: $c-wheat-100;
        color: $c-black-100;
        display: flex;
        flex-direction: column;
        gap: scaling(18);

        .title {
          font-size: scaling(27);
          line-height: scaling(30);
          font-weight: 400;
        }

        .line {
          width: scaling(50);
          height: 2px;
          background-color: $c-black-100;
        }

        .text {
          font-weight: 300;
          line-height: 26px;
        }

        .list {
          margin-top: scaling(18);

          &Item {
            font-weight: 700;
          }
        }

        .link {
          width: max-content;
          background-color: $c-blue-80;
          padding: scaling(10) scaling(36);
          color: $c-white-100;
          display: flex;
          gap: 15px;
          margin-top: scaling(18);

          &::after {
            content: "→";
          }
        }
      }
    }
  }

  @include mobile {
    &-content {
      &--item {
        &:first-child {
          display: none;
        }

        &:last-child {
          padding: scaling(80) scaling(20);
        }
      }
    }
  }
}
</style>