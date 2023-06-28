<template>
  <div class="DefaultBlock" :id="anchor">
    {{ text }}
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      required: true,
    },

    anchor: {
      type: String,
      required: true,
    },
  },
};
</script>


<styled lang="scss" scoped>
.DefaultBlock {
  width: 100%;
  height: 400px;
  border: 2px solid wheat;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 32px;
}
</styled>