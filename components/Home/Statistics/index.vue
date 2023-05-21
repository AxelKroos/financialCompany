<template>
  <div class="Statistics">
    <div class="Statistics-overlay">
      <div class="Statistics-wrapper">
        <div
          class="Statistics-block"
          v-for="(block, i) in blocks"
          :key="i"
          :class="block.isActive ? 'isActive' : ''"
        >
          <h1>{{ block.num }}</h1>
          <div class="Statistics-block--line"></div>
          <h4>{{ block.text }}</h4>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      blocks: [
        {
          num: 6300,
          text: "Совершено сделок",
        },
        {
          num: 1200,
          text: "Корпоративных решений",
        },
        {
          num: 1000,
          text: "Довольных клиентов",
          isActive: true,
        },
        {
          num: 600,
          text: "Партнеров по миру",
        },
      ],
    };
  },
};
</script>

<style scoped lang="scss">
.Statistics {
  background-image: url("~static/img/parallax.webp");
  background-attachment: fixed;
  background-origin: initial;
  background-clip: initial;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;

  &-overlay {
    background-color: rgba(246, 246, 246, 0.9);
  }

  &-wrapper {
    max-width: $w-1170;
    margin: 0 auto;
    display: flex;
  }

  &-block {
    color: $c-black-80;
    width: 25%;
    margin: 0 12px;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 80px 40px;
    transition: background-color 0.2s ease;

    h1 {
      font-size: 40px;
      line-height: 40px;
      font-style: normal;
      font-weight: 300;
    }

    h4 {
      font-size: 22px;
      line-height: 25px;
      font-weight: 400;
      text-align: center;
    }

    &:hover {
      background-color: rgba(0, 0, 0, 0.2);
    }

    &.isActive {
      background-color: rgba(0, 0, 0, 0.2);
    }

    &--line {
      width: 80%;
      height: 1px;
      background-color: #e0e1e2;
      display: block;
      margin: 20px auto;
    }
  }

  @media (max-width: ($bp-tablet - 1)) {
  }
}
</style>