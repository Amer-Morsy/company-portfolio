<template>
  <Navbar />
  <div class="app-body">
    <router-view class="app-content" />
    <Footer />
  </div>
  <ScrollToTop />
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
import ScrollToTop from './components/ScrollToTop.vue';
import {
  getAppLanguage,
  setAppTitle,
  setRootStyleLang,
  setRootStyleTheme,
} from './utils/helper';

export default defineComponent({
  components: { Navbar, Footer, ScrollToTop },
  setup() {
    const { locale } = useI18n({ useScope: 'global' });
    locale.value = getAppLanguage();
    setAppTitle();
    setRootStyleLang();
    setRootStyleTheme();

    // fetch('data/employees.json')
    //   .then((response) => {
    //     return response.json();
    //   })
    //   .then((data) => console.log(data));

    // return { setAppTitle };
  },
});
</script>
