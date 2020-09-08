<template>
  <div class="block-price">
    <img
      v-if="!priceOpen"
      class="block-price__image"
      src="@/assets/factory.svg"
      alt=""
    />
    <v-add-button
      v-if="!priceOpen"
      @click.native="priceOpen = true"
      :text="'Add Pricing'"
      :type="'country-button__add'"
    >
      <div class="big-plus">+</div>
    </v-add-button>
    <div class="block-price__open" v-else>
      <v-price-component :coast="'€30'" :text="'FACTORY PRICE'">
        <img src="@/assets/shop.svg" alt=""
      /></v-price-component>
      x
      <v-price-component :coast="'5.5'" :text="'MARKUP'">
        <img src="@/assets/shop.svg" alt=""
      /></v-price-component>
      =
      <v-price-component :coast="'€185'" :text="'RETAIL PRICE'">
        <img src="@/assets/shop.svg" alt="" />
      </v-price-component>
    </div>
  </div>
</template>
<script>
import VAddButton from '@/components/universal-components/v-add-button'
import VPriceComponent from '@/components/universal-components/v-price-component'

export default {
  components: {
    VAddButton,
    VPriceComponent,
  },
  data: () => ({
    priceOpen: false,
  }),
}
</script>

<style lang="scss">
.block-price {
  display: flex;
  &__open {
    display: flex;
    align-items: center;
    font-weight: 600;
    color: grey;
    font-size: 20px;
  }
  &__image {
    margin-right: 30px;
  }
}
</style>
