<template>
  <div
    class="custom-cards"
    :style="`
      --item-width: ${itemWidth};
      --item-width-tablet: ${itemWidthTablet};
      --item-width-mobile: ${itemWidthMobile};
      --img-width: ${imgWidth};
      --img-height: ${imgHeight};
    `"
  >
    <template v-if="list">
      <template v-for="(item, index) in list" :key="index">
        <div class="custom-card">
          <div class="inner-card">
            <div v-if="item.image" class="image-container">
              <img :src="item.image" />
            </div>
            <h2 v-if="item.title" class="title">{{ item.title }}</h2>
            <p v-if="item.description" class="description">
              {{ item.description }}
            </p>
          </div>
        </div>
      </template>
    </template>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import CustomCard from './../types/CustomCard';
import { ITEMS_WIDTH } from './../utils/constants';

export default defineComponent({
  props: {
    list: { type: Array as PropType<CustomCard[]> },
    itemWidth: { type: String, default: ITEMS_WIDTH.third },
    itemWidthTablet: { type: String, default: ITEMS_WIDTH.half },
    itemWidthMobile: { type: String, default: ITEMS_WIDTH.full },
    imgWidth: { type: String, default: '200px' },
    imgHeight: { type: String, default: '200px' },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/custom-cards.scss';
</style>
