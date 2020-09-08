<template>
  <div
    class="colors__block"
    @mouseenter="
      () => {
        plus = true
      }
    "
    @mouseleave="
      () => {
        plus = false
      }
    "
    @click="addColor"
    :style="{ backgroundColor: item }"
  >
    <div v-if="plus" class="colors__plus">+</div>
  </div>
</template>
<script>
export default {
  props: {
    item: String,
  },
  data: () => ({
    plus: false,
  }),
  methods: {
    addColor() {
      this.$emit('addColor', this.item)
    },
  },
}
</script>

<style lang="scss">
.colors {
  &__block {
    flex: 0 0 20%;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100px;
    cursor: pointer;
  }
  &__plus {
    display: flex;
    width: 20px;
    height: 20px;
    justify-content: center;
    align-items: center;
    border: 1px solid white;
    border-radius: 50%;
    background-color: #35495e;
    color: white;
    font-weight: 600;
  }
}
</style>
