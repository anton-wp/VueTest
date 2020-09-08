<template>
  <div class="product-block__content">
    <div class="product-block__left">
      <v-block-colors />
      <div class="product-block__res">
        <v-block-country />
        <v-block-price style="margin-left: 50px" />
      </div>
    </div>
    <div class="product-block__right">
      <img class="content-image" src="@/assets/pngwing.png" alt="" />

      <v-add-button
        class="product-block__product_add"
        v-if="!imageOpen"
        @click.native="imageOpen = true"
        :text="'Add Product Images'"
        :type="'country-button__add'"
      >
        <div class="big-plus">+</div>
      </v-add-button>
      <div
        class="block-unactive"
        :class="imageOpen ? 'block-unactive__active' : ''"
      ></div>
    </div>
  </div>
</template>

<script>
import VBlockColors from '@/components/page-block/v-block-colors'
import VBlockPrice from '@/components/page-block/v-block-price'
import VBlockCountry from '@/components/page-block/v-block-country'
import VAddButton from '@/components/universal-components/v-add-button'

export default {
  components: {
    VBlockColors,
    VBlockPrice,
    VBlockCountry,
    VAddButton,
  },
  data: () => ({
    imageOpen: false,
  }),
}
</script>
