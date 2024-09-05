<template>
  <header class="section-header">
    <div class="text">
      <h1 class="title">{{ title }}</h1>
      <p class="description">{{ description }}</p>
    </div>
    <div class="image-container">
      <img :src="image" />
    </div>
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    title: { type: String, default: '' },
    description: { type: String, default: '' },
    image: { type: String, default: '' },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/section-header.scss';
</style>
