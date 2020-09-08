<template>
  <div class="product-block">
    <h1 class="title product-block__title">Cap Toe Sneaker</h1>
    <div class="product-block__buttons">
      <button class="button-idea">Idea</button>
      <button class="button-dev">In Development</button>
    </div>

    <div class="product-block__tag"></div>
    <div class="tags-block">
      <v-block-season />
      <v-block-label />
    </div>
    <v-block-content />
  </div>
</template>

<script>
import VBlockSeason from '@/components/page-block/v-block-season'
import VBlockLabel from '@/components/page-block/v-block-label'
import VBlockContent from '@/components/page-block/v-block-content'

export default {
  components: {
    VBlockSeason,
    VBlockLabel,
    VBlockContent,
  },
}
</script>

<style lang="scss">
.title {
  color: #3b4f64;
  font-size: 20px;
  font-weight: 400;
}
.product-block {
  &__title {
    margin: 0 0 10px 0;
    display: inline-block;
  }
  &__res {
    margin-top: 50px;
    display: flex;
  }
  &__left {
    flex: 0 0 50%;
  }
  &__right {
    flex-basis: 0;
    flex-grow: 1;
    min-width: 0;
    max-width: 100%;
    position: relative;
  }
  &__content {
    display: flex;
  }
  &__product_add {
    position: absolute;
    margin-left: auto;
    margin-right: auto;
    left: 0;
    right: 0;
    top: 50%;
    z-index: 1;
  }
  &__buttons {
    display: block;
    margin-left: auto;
    float: right;

    button {
      min-width: 100px;
      border: none;
      border-radius: 10px;
      color: white;
      padding: 5px 10px;
      margin: 0 10px;
    }
    .button-idea {
      background-color: #3a9ddd;
    }
    .button-dev {
      background-color: #f8be6a;
    }
  }
  .content-image {
    width: 100%;
  }
  .block-unactive {
    position: absolute;
    background-color: #f1f1f1;
    opacity: 0.5;
    top: 0;
    right: 0;
    width: 100%;
    height: 100%;

    &__active {
      width: 50% !important;
    }
  }
}
.tags-block {
  display: flex;
}
</style>
