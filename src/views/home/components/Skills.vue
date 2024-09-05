<template>
  <div>
    <SectionHeader
      :title="t('home.skills.header.title')"
      :description="t('home.skills.header.description')"
      :image="imgSkillsHeader"
    />
    <GeneralStatistics :list="GeneralStatisticsList" />
    <div class="container mt-5">
      <CustomCards :list="CustomCardsList" />
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import StatisticsItem from './../../../types/StatisticsItem';
import CustomCard from './../../../types/CustomCard';
import SectionHeader from './../../../components/SectionHeader.vue';
import GeneralStatistics from './../../../components/GeneralStatistics.vue';
import CustomCards from './../../../components/CustomCards.vue';
import {
  imgSkillsHeader,
  imgSkillsExperience,
  imgSkillsCreativeTeam,
  imgSkillsHighQuality,
} from './../../../utils/images';

export default defineComponent({
  components: { SectionHeader, GeneralStatistics, CustomCards },
  setup() {
    const { t } = useI18n();
    const GeneralStatisticsList: StatisticsItem[] = [
      {
        number: t('home.skills.statistics.number1'),
        text: t('home.skills.statistics.text1'),
      },
      {
        number: t('home.skills.statistics.number2'),
        text: t('home.skills.statistics.text2'),
      },
      {
        number: t('home.skills.statistics.number3'),
        text: t('home.skills.statistics.text3'),
      },
      {
        number: t('home.skills.statistics.number4'),
        text: t('home.skills.statistics.text4'),
      },
    ];
    const CustomCardsList: CustomCard[] = [
      {
        title: t('home.skills.cards.title1'),
        description: t('home.skills.cards.description1'),
        image: imgSkillsExperience,
      },
      {
        title: t('home.skills.cards.title2'),
        description: t('home.skills.cards.description2'),
        image: imgSkillsCreativeTeam,
      },
      {
        title: t('home.skills.cards.title3'),
        description: t('home.skills.cards.description3'),
        image: imgSkillsHighQuality,
      },
    ];

    return {
      t,
      imgSkillsHeader,
      GeneralStatisticsList,
      CustomCardsList,
    };
  },
});
</script>
