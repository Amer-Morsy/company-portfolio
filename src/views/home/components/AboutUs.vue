<template>
  <div>
    <SectionHeader
      :title="t('home.aboutUs.header.title')"
      :description="t('home.aboutUs.header.description')"
      :image="imgAboutUsHeader"
    />
    <div class="aboutus-aphorism">
      <Aphorism
        :name="t('home.aboutUs.aphorism.name')"
        :title="t('home.aboutUs.aphorism.title')"
        :text="t('home.aboutUs.aphorism.text')"
        :image="imgEmployeeMohammedOkasha"
      />
    </div>

    <SectionTitle :title="t('home.aboutUs.cards.header')" />
    <div class="container">
      <CustomCards :list="CustomCardsList" imgWidth="100%" imgHeight="350px" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import CustomCard from './../../../types/CustomCard';
import SectionHeader from './../../../components/SectionHeader.vue';
import Aphorism from './../../../components/Aphorism.vue';
import SectionTitle from './../../../components/SectionTitle.vue';
import CustomCards from './../../../components/CustomCards.vue';
import {
  imgAboutUsHeader,
  imgEmployeeMohammedOkasha,
  imgEmployeeAhmedOmar,
  imgEmployeeKareemReda,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionHeader, Aphorism, SectionTitle, CustomCards },
  setup() {
    const { t } = useI18n();
    const CustomCardsList: CustomCard[] = [
      {
        title: t('home.aboutUs.cards.title1'),
        description: t('home.aboutUs.cards.description1'),
        image: imgEmployeeMohammedOkasha,
      },
      {
        title: t('home.aboutUs.cards.title2'),
        description: t('home.aboutUs.cards.description2'),
        image: imgEmployeeAhmedOmar,
      },
      {
        title: t('home.aboutUs.cards.title3'),
        description: t('home.aboutUs.cards.description3'),
        image: imgEmployeeKareemReda,
      },
    ];

    return { t, imgAboutUsHeader, imgEmployeeMohammedOkasha, CustomCardsList };
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/home-aboutus.scss';
</style>
