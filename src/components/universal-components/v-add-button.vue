<template>
  <div class="button-add" :class="type">
    <slot />
    <span class="button-add__text">{{ text }}</span>
  </div>
</template>
<script>
export default {
  props: {
    text: String,
    img: String,
    type: String,
  },
}
</script>

<style lang="scss">
.button-add {
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px dashed #3b4f64;
  border-radius: 10px;
  max-width: 200px;
  width: 100%;
  background-color: #f8f8f8;
  &__text {
    margin-left: 10px;
  }
}
.color-button {
  &__add {
    padding: 10px 30px;
  }
}
.country-button {
  &__add {
    padding: 20px 30px;
  }
}
</style>
