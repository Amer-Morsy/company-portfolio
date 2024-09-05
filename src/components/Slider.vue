<template>
  <div class="slider">
    <div :id="id" class="carousel slide" data-bs-ride="false">
      <div class="carousel-indicators">
        <template v-if="list">
          <template v-for="(item, index) in list" :key="index">
            <button
              type="button"
              :data-bs-target="`#${id}`"
              :data-bs-slide-to="index"
              :class="item.activeStatus ? 'active' : ''"
              aria-current="true"
            ></button>
          </template>
        </template>
      </div>

      <div class="carousel-inner">
        <template v-if="list">
          <template v-for="(item, index) in list" :key="index">
            <div
              class="carousel-item"
              :class="item.activeStatus ? 'active' : ''"
            >
              <img :src="item.image" alt="..." />
              <div
                v-if="item.title || item.description"
                class="carousel-caption"
              >
                <h1>{{ item.title }}</h1>
                <p>{{ item.description }}</p>
              </div>
            </div>
          </template>
        </template>
      </div>

      <button
        class="carousel-control-prev"
        type="button"
        :data-bs-target="`#${id}`"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      </button>
      <button
        class="carousel-control-next"
        type="button"
        :data-bs-target="`#${id}`"
        data-bs-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
      </button>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Slide from './../types/Slide';

export default defineComponent({
  props: {
    id: { type: String, default: 'carouselExampleCaptions' },
    list: { type: Array as PropType<Slide[]> },
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/slider.scss';
</style>
