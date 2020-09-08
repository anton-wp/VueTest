<template>
  <div>
    <v-tag
      v-if="!tagLabelActive"
      @click.native="openLabel()"
      :data="tagLabel"
    />
    <v-tag
      v-else-if="tagLabelActive"
      v-for="(tag, index) in tagLabel.children.slice(0, 3)"
      :key="index"
      :data="tag"
    />
    <v-tag
      v-if="tagLabelActive && tagLabel.children.length > 3"
      :data="counterData()"
    />
  </div>
</template>

<script>
import VTag from '@/components/universal-components/v-tag'
export default {
  components: {
    VTag,
  },
  data: () => ({
    tagLabelActive: false,
    tagLabel: {
      name: '+ Add Label',
      image: true,
      big: true,
      style: {
        color: '#FFFFFF',
        border: 'none',
        background: '#B5B5B5',
      },
      children: [
        {
          name: 'Core',
          big: true,
          img: './plus.svg',
          style: {
            color: '#FFFFFF',
            border: 'none',
            background: '#8AC972',
          },
        },
        {
          name: 'Waterproof',
          big: true,
          style: {
            color: '#FFFFFF',
            border: 'none',
            background: '#507BAC',
          },
        },
        {
          name: 'Vegan',
          big: true,
          style: {
            color: '#3B4F64',
            border: 'none',
            background: '#6CA04B',
          },
        },
        {
          name: 'Core',
          big: true,
          style: {
            color: '#FFFFFF',
            border: 'none',
            background: '#8AC972',
          },
        },
        {
          name: 'Core',
          big: true,
          style: {
            color: '#FFFFFF',
            border: 'none',
            background: '#8AC972',
          },
        },
      ],
    },
  }),
  methods: {
    openLabel() {
      this.tagLabelActive = true
    },
    counterData() {
      return {
        name: `+ ${this.tagLabel.children.length - 3}`,
        style: {
          color: '#FFFFFF',
          border: 'none',
          background: '#B5B5B5',
        },
      }
    },
  },
}
</script>
