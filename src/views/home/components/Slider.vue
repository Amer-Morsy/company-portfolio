<template>
  <Slider id="slider1" :list="list" />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import Slide from './../../../types/Slide';
import Slider from './../../../components/Slider.vue';
import {
  imgHomeslider1,
  imgHomeslider2,
  imgHomeslider3,
  imgHomeslider4,
} from './../../../utils/images';

export default defineComponent({
  components: { Slider },
  setup() {
    const { t } = useI18n();
    const list: Slide[] = [
      {
        activeStatus: true,
        title: t('home.slider.description1'),
        description: '',
        image: imgHomeslider1,
      },
      {
        activeStatus: false,
        title: t('home.slider.description2'),
        description: '',
        image: imgHomeslider2,
      },
      {
        activeStatus: false,
        title: t('home.slider.description3'),
        description: '',
        image: imgHomeslider3,
      },
      {
        activeStatus: false,
        title: t('home.slider.description4'),
        description: '',
        image: imgHomeslider4,
      },
    ];

    return { list };
  },
});
</script>
