<template>
  <div class="price-component">
    <slot />
    <h3 class="price-component__coast">{{ coast }}</h3>
    <span class="price-component__text">{{ text }}</span>
  </div>
</template>

<script>
export default {
  props: {
    coast: String,
    text: String,
  },
}
</script>

<style lang="scss">
.price-component {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 10px;
  &__coast {
    margin: 0;
    font-size: 20px;
    color: #3b4f64;
  }

  &__text {
    font-size: 12px;
    color: #3b4f64;
    text-align: center;
    white-space: nowrap;
    font-weight: 400;
  }
}
</style>
