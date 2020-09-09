<template>
  <div class="block-colors">
    <h2 class="block-colors__title">COLORS</h2>
    <v-add-button
      v-if="!activeColor.length"
      style="max-width: 120px"
      :text="'Add'"
      :type="'color-button__add'"
      @click.native="openColorModal()"
    >
      <img src="@/assets/color.png" alt="" />
    </v-add-button>
    <div class="block-colors__tags">
      <div
        v-for="(color, index) in activeColor.slice(0, 6)"
        :key="index"
        class="color-tag"
        :style="{ backgroundColor: color }"
      >
        {{ color }}
      </div>
      <div class="color-count" v-if="activeColor.length > 6">
        +{{ activeColor.length - 6 }}
      </div>
    </div>
    <v-color-modal
      v-if="colorModal"
      @closeColorModal="closeColorModal()"
      @saveColor="saveColor"
    />
  </div>
</template>

<script>
import VAddButton from '@/components/universal-components/v-add-button'
import VColorModal from '@/components/modal/v-color-modal'

export default {
  components: {
    VAddButton,
    VColorModal,
  },
  data: () => ({
    colorModal: false,
    activeColor: [],
  }),
  methods: {
    openColorModal() {
      this.colorModal = true
    },
    closeColorModal() {
      this.colorModal = false
    },
    saveColor(colors) {
      this.activeColor = colors
      this.colorModal = false
    },
  },
}
</script>

<style lang="scss">
.block-colors {
  margin-top: 50px;
  &__title {
    font-size: 14px;
    color: #3b4f64;
    font-weight: 400;
  }
  &__tags {
    width: 400px;
    display: flex;
    flex-wrap: wrap;
    .color-tag {
      flex: 0 0 25%;
      display: flex;
      justify-content: center;
      margin: 5px 10px 5px 0;
      border-radius: 10px;
      padding: 3px 5px;
    }
    .color-count {
      color: #3b4f64;
      border: 1px solid #3b4f64;
      background-color: white;
      border-radius: 50%;
      width: 25px;
      height: 25px;
      font-size: 12px;
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 5px;
    }
  }
}
</style>
