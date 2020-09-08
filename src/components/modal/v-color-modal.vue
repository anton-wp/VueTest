<template>
  <div class="color-modal">
    <div class="color-modal__block">
      <div class="color-modal__colors">
        <div class="colors">
          <v-block-color
            v-for="item in color"
            :key="item"
            :item="item"
            @addColor="addColor"
          />
        </div>
      </div>
      <div class="color-modal__control">
        <h1 class="title">Selected Colors</h1>

        <div class="color-modal__color_active">
          <div v-for="(color, index) in activeColors" :key="index">
            <v-block-active-color @delColor="delColor" :item="color" />
          </div>
        </div>

        <div class="color-modal__buttons">
          <button class="button-cancel" @click="close">
            <img src="@/assets/close.svg" alt="" />
            CANCEL
          </button>
          <button class="button-save" @click="save">
            <img src="@/assets/save.svg" alt="" />
            SAVE
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VBlockColor from '@/components/modal/v-block-color'
import VBlockActiveColor from '@/components/modal/v-block-active-color'
export default {
  components: {
    VBlockColor,
    VBlockActiveColor,
  },
  data: () => ({
    color: [
      '#FBFBFB',
      '#FF0000',
      '#00FF00',
      '#0000FF',
      '#FF9D00',
      '#C0C0C0',
      '#800000',
      '#008000',
      '#000080',
      '#AA6900',
      '#808080',
      '#FFDF72',
      '#0EBA00',
      '#C371FF',
      '#00FF89',
      '#484848',
      '#FFFF00',
      '#00FFFF',
      '#FF00FF',
      '#00AF5E',
      '#000000',
      '#808000',
      '#008080',
      '#800080',
      '#10643D',
    ],
    activeColors: [],
  }),
  methods: {
    close() {
      this.$emit('closeColorModal')
    },
    save() {
      this.$emit('saveColor', this.activeColors)
    },
    addColor(color) {
      this.activeColors.push(color)
    },
    delColor(color) {
      const idx = this.activeColors.findIndex((c) => c.color === color)

      this.activeColors.splice(idx, 1)
    },
  },
}
</script>

<style lang="scss">
.color-modal {
  position: fixed;
  z-index: 2;
  display: flex;
  justify-content: center;
  width: 100%;
  height: 100%;
  background-color: white;
  top: 0;
  left: 0;
  padding: 20px;
  &__block {
    position: absolute;
    overflow: hidden;
    display: flex;
    width: 100%;
    max-width: 900px;
    background-color: white;
    opacity: 1;
    z-index: 1;
    box-shadow: 0 0 50px 10px rgba(0, 0, 0, 0.4);
    border-radius: 10px;
  }
  &__colors {
    flex: 0 0 60%;
    padding: 30px;
    background-color: #fafafa;
  }
  &__control {
    width: 100%;
    padding-left: 20px;
  }
  &__color_active {
    overflow-y: scroll;
    height: 400px;
  }
  &__buttons {
    justify-content: space-between;
    display: flex;
    padding: 20px;
    button {
      padding: 5px 20px;
      border-radius: 20px;
      border: 1px solid #35495e;
      display: flex;
      cursor: pointer;
      img {
        margin-right: 5px;
      }
    }
    .button-cancel {
      background-color: white;
      color: #35495e;
    }
    .button-save {
      background-color: #35495e;
      color: white;
    }
  }
}
.colors {
  width: 500px;
  height: 500px;
  display: flex;
  flex-wrap: wrap;
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid black;
}
</style>
