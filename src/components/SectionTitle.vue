<template>
  <header class="section-title">
    <h1 class="title">{{ title }}</h1>
    <CustomDivider />
  </header>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import CustomDivider from './CustomDivider.vue';

export default defineComponent({
  components: { CustomDivider },
  props: {
    title: { type: String, default: '' },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/section-title.scss';
</style>
