<template>
  <div>
    <SectionHeader
      :title="t('home.projects.header.title')"
      :description="t('home.projects.header.description')"
      :image="imgProjectsHeader"
    />
    <div class="container">
      <CustomCards :list="CustomCardsList" imgWidth="100%" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import CustomCard from './../../../types/CustomCard';
import SectionHeader from './../../../components/SectionHeader.vue';
import CustomCards from './../../../components/CustomCards.vue';
import {
  imgProjectsHeader,
  imgClientNileVocationalAcademy,
  imgClientAlmokawloonAlarab,
  imgClientArcplanGroup,
  imgClientAlsharq,
  imgClientAjiad,
  imgClientPremcoPrecast,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionHeader, CustomCards },
  setup() {
    const { t } = useI18n();
    const CustomCardsList: CustomCard[] = [
      {
        title: t('home.projects.cards.title1'),
        description: t('home.projects.cards.description1'),
        image: imgClientNileVocationalAcademy,
      },
      {
        title: t('home.projects.cards.title2'),
        description: t('home.projects.cards.description2'),
        image: imgClientAlmokawloonAlarab,
      },
      {
        title: t('home.projects.cards.title3'),
        description: t('home.projects.cards.description3'),
        image: imgClientArcplanGroup,
      },
      {
        title: t('home.projects.cards.title4'),
        description: t('home.projects.cards.description4'),
        image: imgClientAlsharq,
      },
      {
        title: t('home.projects.cards.title5'),
        description: t('home.projects.cards.description5'),
        image: imgClientAjiad,
      },
      {
        title: t('home.projects.cards.title6'),
        description: t('home.projects.cards.description6'),
        image: imgClientPremcoPrecast,
      },
    ];

    return {
      t,
      imgProjectsHeader,
      CustomCardsList,
    };
  },
});
</script>
