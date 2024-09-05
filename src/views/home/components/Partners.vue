<template>
  <div>
    <SectionHeader
      :title="t('home.partners.header.title')"
      :description="t('home.partners.header.description')"
      :image="imgPartnersHeader"
    />
    <div class="container">
      <CustomCards
        :list="CustomCardsList"
        imgWidth="100%"
        imgHeight="150px"
        :itemWidth="ITEMS_WIDTH.quarter"
        :itemWidthTablet="ITEMS_WIDTH.half"
      />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import { ITEMS_WIDTH } from './../../../utils/constants';
import CustomCard from './../../../types/CustomCard';
import SectionHeader from './../../../components/SectionHeader.vue';
import CustomCards from './../../../components/CustomCards.vue';
import {
  imgPartnersHeader,
  imgPartnerSky,
  imgPartnerCooplies,
  imgPartnerSIG,
  imgPartnerHuawei,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionHeader, CustomCards },
  setup() {
    const { t } = useI18n();
    const CustomCardsList: CustomCard[] = [
      {
        title: '',
        description: '',
        image: imgPartnerSky,
      },
      {
        title: '',
        description: '',
        image: imgPartnerCooplies,
      },
      {
        title: '',
        description: '',
        image: imgPartnerSIG,
      },
      {
        title: '',
        description: '',
        image: imgPartnerHuawei,
      },
    ];

    return { t, ITEMS_WIDTH, imgPartnersHeader, CustomCardsList };
  },
});
</script>
