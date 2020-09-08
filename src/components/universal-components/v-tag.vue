<template>
  <div
    class="tag"
    :class="data.big ? 'tag__big' : 'tag__small'"
    :style="{
      border: data.style.border,
      color: data.style.color,
      backgroundColor: data.style.background,
    }"
  >
    {{ data.name }}
  </div>
</template>

<script>
export default {
  props: {
    data: Object,
  },
}
</script>
<style lang="scss">
.tag {
  display: inline-block;
  border-radius: 5px;
  font-size: 12px;
  cursor: pointer;
  margin: 0 5px;
  text-align: center;
  padding: 5px;
  &__small {
    min-width: 20px;
  }
  &__big {
    min-width: 70px;
  }
}
</style>
