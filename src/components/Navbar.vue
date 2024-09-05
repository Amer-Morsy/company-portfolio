<template>
  <div class="app-navbar">
    <input type="checkbox" id="nav-check" />
    <div class="nav-header">
      <div class="logo-container">
        <img :src="imgLogo" />
      </div>
      <div class="nav-title">{{ t('general.projectName') }}</div>
    </div>
    <div class="nav-btn">
      <label for="nav-check">
        <span></span>
        <span></span>
        <span></span>
      </label>
    </div>

    <div class="nav-links">
      <router-link :to="{ name: 'Home' }">{{ t('navbar.Home') }}</router-link>
      <router-link :to="{ name: 'About' }">{{
        t('navbar.Services')
      }}</router-link>
      <router-link :to="{ name: 'About' }">{{
        t('navbar.Projects')
      }}</router-link>
      <router-link :to="{ name: 'About' }">{{
        t('navbar.ClientsAndPartners')
      }}</router-link>
      <router-link :to="{ name: 'About' }">{{
        t('navbar.AboutUs')
      }}</router-link>
      <router-link :to="{ name: 'About' }">{{
        t('navbar.ContactUs')
      }}</router-link>

      <!-- #region Language -->
      <button
        v-if="language == LANGUAGES.enUS"
        @click="setAppLanguage(LANGUAGES.arEG)"
        class="icon"
      >
        <img src="./../assets/images/lang-ar.svg" />
      </button>
      <button
        v-if="language == LANGUAGES.arEG"
        @click="setAppLanguage(LANGUAGES.enUS)"
        class="icon"
      >
        <img src="./../assets/images/lang-en.svg" />
      </button>
      <!-- #endregion Language -->

      <!-- #region Theme -->
      <button
        v-if="theme == THEMES.dark"
        @click="setAppTheme(THEMES.light)"
        class="icon-theme"
      >
        <img src="./../assets/images/theme-light.svg" />
      </button>
      <button
        v-if="theme == THEMES.light"
        @click="setAppTheme(THEMES.dark)"
        class="icon-theme"
      >
        <img src="./../assets/images/theme-dark.svg" />
      </button>
      <!-- #endregion Theme -->
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import { LANGUAGES, THEMES } from './../utils/constants';
import {
  getAppLanguage,
  setAppLanguage,
  getAppTheme,
  setAppTheme,
  shrinkNavbar,
} from './../utils/helper';
import { imgLogo } from './../utils/images';

export default defineComponent({
  setup() {
    const { t } = useI18n();
    const language = getAppLanguage();
    const theme = getAppTheme();
    shrinkNavbar();

    return {
      t,
      LANGUAGES,
      language,
      THEMES,
      theme,
      setAppLanguage,
      setAppTheme,
      imgLogo,
    };
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/navbar.scss';
</style>
