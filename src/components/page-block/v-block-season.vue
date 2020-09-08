<template>
  <div>
        <v-tag
          v-if="!tagSeasonActive"
          @click.native="openSeason()"
          :data="tagSeason"
        />
        <v-tag
          v-else-if="tagSeasonActive"
          v-for="(tag, index) in tagSeason.children.slice(3)"
          :key="index"
          :data="tag"
        />
        <v-tag
          v-if="tagSeasonActive && tagSeason.children.length > 3"
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
    tagSeasonActive: false,
    tagSeason: {
      name: '+ Add Season',
      image: true,
      big: true,
      style: {
        color: '#3B4F64',
        border: 'none',
        background: '#FFFFFF',
      },
      children: [
        {
          name: 'AW21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #A5B2D7',
            background: '#FFFFFF',
          },
        },
        {
          name: 'AW21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #A5B2D7',
            background: '#FFFFFF',
          },
        },
        {
          name: 'AW21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #A5B2D7',
            background: '#FFFFFF',
          },
        },
        {
          name: 'AW21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #A5B2D7',
            background: '#FFFFFF',
          },
        },
        {
          name: 'SS21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #F2E5B9',
            background: '#FFFFFF',
          },
        },
        {
          name: 'AW21',
          big: true,
          style: {
            color: '#3B4F64',
            border: '1px solid #A5B2D7',
            background: '#FFFFFF',
          },
        },
      ],
    },
  }),
  methods: {
    openSeason() {
      this.tagSeasonActive = true
    },
    counterData() {
      return {
        name: `+ ${this.tagSeason.children.length - 3}`,
        style: {
          color: '#3B4F64',
          border: '1px solid #A5B2D7',
          background: '#FFFFFF',
        },
      }
    },
  },
}
</script>