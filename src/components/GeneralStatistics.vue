<template>
  <div
    class="general-statistics"
    :style="`
      --item-width: ${itemWidth};
      --item-width-tablet: ${itemWidthTablet};
      --item-width-mobile: ${itemWidthMobile};
    `"
  >
    <template v-if="list">
      <template v-for="(item, index) in list" :key="index">
        <div class="statistics-item">
          <h1>{{ item.number }}</h1>
          <h3>{{ item.text }}</h3>
        </div>
      </template>
    </template>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import StatisticsItem from './../types/StatisticsItem';
import { ITEMS_WIDTH } from './../utils/constants';

export default defineComponent({
  props: {
    list: { type: Array as PropType<StatisticsItem[]> },
    itemWidth: { type: String, default: ITEMS_WIDTH.quarter },
    itemWidthTablet: { type: String, default: ITEMS_WIDTH.third },
    itemWidthMobile: { type: String, default: ITEMS_WIDTH.half },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/general-statistics.scss';
</style>
