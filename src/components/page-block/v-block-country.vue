<template>
  <div class="block-country">
    <img class="block-country__image" src="@/assets/factory.svg" alt="" />
    <v-add-button
      v-if="!countryOpen"
      @click.native="countryOpen = true"
      :text="'Add Suplier'"
      :type="'country-button__add'"
    >
      <div class="big-plus">+</div>
    </v-add-button>
    <div v-else class="block-country__blocks">
      <div v-for="(country, index) in country.slice(0, 2)" :key="index">
        <img class="block-country__flag" :src="country.img" alt="" />
        <span class="block-country__name">{{ country.name }}</span>
      </div>
      <span class="block-country__more" v-if="country.length > 2"
        >+ {{ country.length - 2 }} MORE</span
      >
    </div>
  </div>
</template>
<script>
import VAddButton from '@/components/universal-components/v-add-button'

export default {
  components: {
    VAddButton,
  },
  data: () => ({
    countryOpen: false,
    country: [
      {
        id: 1,
        name: 'Albano Perreira',
        img:
          'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAP8AAACqCAMAAABVlWm8AAAACVBMVEUAkkb////OKzdsRJOSAAAAxklEQVR4nO3PMQEAAAjAILV/aFPsgwbMFLZwhaTv7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v75/+HwW0qVdTeFEnAAAAAElFTkSuQmCC',
      },
      {
        id: 2,
        name: 'Shoelutions',
        img:
          'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAP8AAACqCAMAAABVlWm8AAAACVBMVEUAkkb////OKzdsRJOSAAAAxklEQVR4nO3PMQEAAAjAILV/aFPsgwbMFLZwhaTv7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v75/+HwW0qVdTeFEnAAAAAElFTkSuQmCC',
      },
      {
        id: 3,
        name: 'Albano Perreira',
        img:
          'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAP8AAACqCAMAAABVlWm8AAAACVBMVEUAkkb////OKzdsRJOSAAAAxklEQVR4nO3PMQEAAAjAILV/aFPsgwbMFLZwhaTv7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v75/+HwW0qVdTeFEnAAAAAElFTkSuQmCC',
      },
      {
        id: 4,
        name: 'Albano Perreira',
        img:
          'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAP8AAACqCAMAAABVlWm8AAAACVBMVEUAkkb////OKzdsRJOSAAAAxklEQVR4nO3PMQEAAAjAILV/aFPsgwbMFLZwhaTv7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v7+/v75/+HwW0qVdTeFEnAAAAAElFTkSuQmCC',
      },
    ],
  }),
}
</script>

<style lang="scss">
.block-country {
  display: flex;
  &__image {
    margin-right: 30px;
  }
  &__blocks {
    display: flex;
    flex-direction: column;
    margin: 5px 0;
  }
  &__flag {
    width: 20px;
    height: 15px;
    margin-right: 10px;
  }
  &__name {
    color: #3b4f64;
  }
  &__more {
    font-size: 12px;
    color: #a5b2d7;
    text-align: center;
  }
}
.big-plus {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 25px;
  height: 25px;
  background-color: #3b4f64;
  border-radius: 50%;
  color: white;
  font-weight: 600;
  font-size: 1rem;
}
</style>
