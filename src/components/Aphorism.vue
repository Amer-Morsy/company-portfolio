<template>
  <div class="aphorism">
    <div class="aphorism-title">
      <div class="image-container">
        <img :src="image" />
      </div>
      <div class="text">
        <h3 class="name">{{ name }}</h3>
        <p class="title">{{ title }}</p>
      </div>
    </div>
    <div class="aphorism-text">
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  props: {
    name: { type: String, default: '' },
    title: { type: String, default: '' },
    text: { type: String, default: '' },
    image: { type: String, default: '' },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/aphorism.scss';
</style>
