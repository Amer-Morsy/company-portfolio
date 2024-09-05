<template>
  <div>
    <SectionHeader
      :title="t('home.clients.header.title')"
      :description="t('home.clients.header.description')"
      :image="imgClientsHeader"
    />
    <div class="container">
      <CustomCards :list="CustomCardsList" />
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
  imgClientsHeader,
  imgClientLogoSky,
  imgClientLogoSportStar,
  imgClientLogoDQuick,
  imgClientLogoArcplanGroup,
  imgClientLogoRefit,
  imgClientLogoApache,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionHeader, CustomCards },
  setup() {
    const { t } = useI18n();
    const CustomCardsList: CustomCard[] = [
      {
        title: t('home.clients.cards.title1'),
        description: t('home.clients.cards.description1'),
        image: imgClientLogoSky,
      },
      {
        title: t('home.clients.cards.title2'),
        description: t('home.clients.cards.description2'),
        image: imgClientLogoSportStar,
      },
      {
        title: t('home.clients.cards.title3'),
        description: t('home.clients.cards.description3'),
        image: imgClientLogoDQuick,
      },
      {
        title: t('home.clients.cards.title4'),
        description: t('home.clients.cards.description4'),
        image: imgClientLogoArcplanGroup,
      },
      {
        title: t('home.clients.cards.title5'),
        description: t('home.clients.cards.description5'),
        image: imgClientLogoRefit,
      },
      {
        title: t('home.clients.cards.title6'),
        description: t('home.clients.cards.description6'),
        image: imgClientLogoApache,
      },
    ];

    return {
      t,
      imgClientsHeader,
      CustomCardsList,
    };
  },
});
</script>
