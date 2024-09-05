<template>
  <div>
    <SectionTitle :title="t('home.services.header.title')" />

    <div class="container">
      <CustomCards :list="CustomCardsList" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import CustomCard from './../../../types/CustomCard';
import SectionTitle from './../../../components/SectionTitle.vue';
import CustomCards from './../../../components/CustomCards.vue';
import {
  imgServicesDesktopApplications,
  imgServicesMobileApplications,
  imgServicesWebApplications,
  imgServicesDesigning,
  imgServicesSEO,
  imgServicesEMarketing,
  imgServicesEmbeddedSystems,
  imgServicesWebHosting,
  imgServicesTechSupport,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionTitle, CustomCards },
  setup() {
    const { t } = useI18n();
    const CustomCardsList: CustomCard[] = [
      {
        title: '',
        description: t('home.services.cards.title1'),
        image: imgServicesDesktopApplications,
      },
      {
        title: '',
        description: t('home.services.cards.title2'),
        image: imgServicesMobileApplications,
      },
      {
        title: '',
        description: t('home.services.cards.title3'),
        image: imgServicesWebApplications,
      },
      {
        title: '',
        description: t('home.services.cards.title4'),
        image: imgServicesDesigning,
      },
      {
        title: '',
        description: t('home.services.cards.title5'),
        image: imgServicesSEO,
      },
      {
        title: '',
        description: t('home.services.cards.title6'),
        image: imgServicesEMarketing,
      },
      {
        title: '',
        description: t('home.services.cards.title7'),
        image: imgServicesEmbeddedSystems,
      },
      {
        title: '',
        description: t('home.services.cards.title8'),
        image: imgServicesWebHosting,
      },
      {
        title: '',
        description: t('home.services.cards.title9'),
        image: imgServicesTechSupport,
      },
    ];

    return { t, CustomCardsList };
  },
});
</script>
