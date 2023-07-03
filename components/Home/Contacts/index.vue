<template>
  <div class="Contacts" :id="anchor">
    <div class="Contacts-map">
      <yandex-map
        :coords="[55.81321056581145, 37.62736939055693]"
        style="width: 100%; height: 100%"
        zoom="12"
      >
        <ymap-marker
          marker-id="1"
          marker-type="placemark"
          :coords="[55.832136, 37.65055]"
          hint-content="Hint content 1"
          :balloon="{
            header: 'Главный офис',
            body: 'ул. Проспект Мира, д. 131, офис 3',
          }"
          :icon="{ color: 'green', glyph: 'office' }"
          cluster-name="1"
        ></ymap-marker>

        <ymap-marker
          marker-id="2"
          marker-type="placemark"
          :coords="[55.781398, 37.598537]"
          hint-content="Hint content 1"
          :balloon="{
            header: 'Филиал',
            body: 'ул. Новослободская, д. 23, офис 535',
          }"
          :icon="{ color: 'green', glyph: 'office' }"
          cluster-name="1"
        ></ymap-marker>
      </yandex-map>
    </div>
    <div class="Contacts-info">
      <div class="Contacts-info--title">КОНТАКТЫ</div>

      <div class="Contacts-info--text">
        <div class="Contacts-info--textItem">
          Главный офис:
          <div class="Contacts-info--textItemSmall">
            г. Москва. ул. Проспект Мира 131, офис 3
          </div>
        </div>

        <div class="Contacts-info--textItem">
          Филиал:
          <div class="Contacts-info--textItemSmall">
            Новослободская ул., д. 23, офис 535
          </div>
        </div>

        <div class="Contacts-info--textItem">
          Телефон:
          <div class="Contacts-info--textItemSmall">+7(499) 755-62-75</div>
        </div>

        <div class="Contacts-info--textItem">
          Электронная почта:
          <div class="Contacts-info--textItemSmall">info@fcrusfin.ru</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { yandexMap, ymapMarker } from "vue-yandex-maps";
// import Popup from "./Popup.vue";

export default {
  props: {
    anchor: {
      type: String,
      required: true,
    },
  },

  components: { yandexMap, ymapMarker },

  data() {
    return {};
  },
};
</script>

<style scoped lang="scss">
.Contacts {
  $component: &;

  display: flex;

  &-map {
    position: relative;
    width: 60%;
  }

  &-info {
    flex: 1;
    padding: 40px;
    display: flex;
    flex-direction: column;
    gap: 40px;

    &--title {
      font-size: 32px;
    }

    &--text {
      display: flex;
      flex-direction: column;
      gap: 20px;

      &Item {
        font-size: 20px;
        font-weight: 500;
        transition: color 0.2s ease;

        &:hover {
          color: wheat;
        }

        &Small {
          font-size: 18px;
          font-weight: 400;
        }
      }
    }
  }

  @include mobile {
    flex-direction: column;

    &-map {
      width: 100%;
    }
  }
}
</style>