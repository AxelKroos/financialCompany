<template>
  <div class="Slider" @mouseover="hover = true" @mouseleave="hover = false">
    <div class="Slider-mask" :class="isRender ? 'notVisible' : ''"></div>

    <div
      class="Slider-wrapper"
      :style="{
        width: content.length * 100 + '%',
        'margin-left': `-${100 * currentSlide}%`,
      }"
    >
      <div v-for="(elem, idx) in content" :key="idx" class="Slider-block">
        <div class="Slider-block--text">
          <h3
            class="Slider-block--textTitle"
            v-text="elem.title"
            :class="currentSlide === idx ? 'isActive' : ''"
          ></h3>
          <h3
            class="Slider-block--textSubtitle"
            :class="currentSlide === idx ? 'isActive' : ''"
            v-text="elem.subtitle"
          ></h3>
          <h3
            class="Slider-block--textContent"
            :class="currentSlide === idx ? 'isActive' : ''"
            v-html="elem.content"
          ></h3>
        </div>
        <img :src="require(`~/static/img/${elem.photo}`)" alt="" />
      </div>
    </div>

    <div class="Slider-options" :class="hover ? 'isVisible' : ''">
      <Arrows :prevSlide="prevSlide" :nextSlide="nextSlide" />
      <Dots
        :content="content"
        :currentSlide="currentSlide"
        :selectSlide="selectSlide"
      />
    </div>
  </div>
</template>

<script>
import Arrows from "./Arrows";
import Dots from "./Dots";

export default {
  components: { Arrows, Dots },

  data() {
    return {
      timer: null,
      interval: null,
      isThrottled: null,
      isRender: false,
      currentSlide: null,
      content: [
        {
          title: "РАЗВИВАЙТЕ СВОЙ БИЗНЕС",
          subtitle: "В КОММЕРЧЕСКИХ ПРОЕКТАХ",
          content:
            "<p>Профессиональная команда, работающая в формате правового бутика</p><p>Предоставляя услуги в области права и налогов.</p>",
          photo: "first.webp",
        },
        {
          title: "МЕЖДУНАРОДНАЯ ПРАКТИКА",
          subtitle: "В СФЕРЕ ФИНАНСОВ",
          content:
            "<p>Профессиональная команда, работающая в формате правового бутика</p><p>Предоставляя услуги в области права и налогов.</p>",
          photo: "second.webp",
        },
        {
          title: "ИЗБРАННЫЕ ПРОЕКТЫ",
          subtitle: "С НАШИМ УЧАСТИЕМ",
          content:
            "<p>Профессиональная команда, работающая в формате правового бутика</p><p>Предоставляя услуги в области права и налогов.</p>",
          photo: "three.webp",
        },
      ],
      hover: false,
    };
  },

  watch: {
    hover() {
      if (this.hover) {
        clearInterval(this.interval);
        this.interval = null;
      } else {
        this.interval = setInterval(() => {
          this.nextSlide();
        }, 10000);
      }
    },
  },

  mounted() {
    clearTimeout(this.timer);
    this.timer = setTimeout(() => {
      this.isRender = true;
      this.currentSlide = 0;

      this.interval = setInterval(() => {
        this.nextSlide();
      }, 10000);
    }, 200);
  },

  methods: {
    prevSlide() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      } else {
        this.currentSlide = this.content.length - 1;
      }
    },

    nextSlide() {
      if (this.currentSlide < this.content.length - 1) {
        this.currentSlide++;
      } else {
        this.currentSlide = 0;
      }
    },

    selectSlide(i) {
      this.currentSlide = i;
    },
  },
};
</script>

<style scoped lang="scss">
@keyframes toRight {
  from {
    opacity: 0;
    transform: translateX(-50%);
  }

  to {
    opacity: 1;
    transform: translateX(0%);
  }
}

@keyframes toLeft {
  from {
    opacity: 0;
    transform: translateX(50%);
  }

  to {
    opacity: 1;
    transform: translateX(0%);
  }
}
.Slider {
  $component: &;

  position: relative;
  width: 100%;
  height: scaling(570);
  overflow: hidden;

  &-mask {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    background-color: white;
    opacity: 1;
    transition: opacity 1s ease;
  }

  .notVisible {
    opacity: 0;
  }

  &-wrapper {
    display: flex;
    transition: margin 0.2s cubic-bezier(1, 0, 0, 1);
  }

  &-block {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    height: scaling(570);

    &--text {
      position: absolute;
      top: 25%;
      display: flex;
      flex-direction: column;
      gap: 16px;

      &Title {
        font-size: scaling(18);
        line-height: scaling(20);
        opacity: 0;
        transform: translateX(-50%);
        text-align: center;
        &.isActive {
          animation: toRight 0.6s ease 0.5s forwards;
        }
      }

      &Subtitle {
        font-size: scaling(36);
        line-height: scaling(40);
        font-weight: 500;
        opacity: 0;
        transform: translateX(50%);
        text-align: center;
        &.isActive {
          animation: toLeft 0.6s ease 1.1s forwards;
        }
      }

      &Content {
        font-size: scaling(12);
        line-height: scaling(20);
        font-weight: 400;
        opacity: 0;
        transform: translateX(-50%);
        text-align: center;
        &.isActive {
          animation: toRight 0.6s ease 1.7s forwards;
        }
      }
    }

    img {
      width: 100%;
      margin-top: scaling(-100);
    }
  }

  &-options {
    opacity: 0;
    transition: opacity 0.5s ease;

    &.isVisible {
      opacity: 1;
    }
  }
}
</style>
