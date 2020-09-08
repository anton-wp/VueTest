<template>
  <div class="colors-active">
    <div class="colors-active__color" :style="{ backgroundColor: item }"></div>
    <img
      class="colors-active__delete"
      @click="delColor"
      src="@/assets/delete.svg"
      alt=""
    />
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
    delColor() {
      this.$emit('delColor', this.item)
    },
  },
}
</script>

<style lang="scss">
.colors-active {
  display: flex;
  justify-content: space-between;
  padding-right: 35px;
  &__color {
    width: 100px;
    height: 100px;
  }
  &__delete {
    cursor: pointer;
  }
}
</style>
