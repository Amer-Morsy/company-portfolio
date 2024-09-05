<template>
  <div class="home">
    <Slider />
    <Skills />
    <Services />
    <Projects />
    <Clients />
    <Partners />
    <AboutUs />
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import Slider from './components/Slider.vue';
import Skills from './components/Skills.vue';
import Services from './components/Services.vue';
import Projects from './components/Projects.vue';
import Clients from './components/Clients.vue';
import Partners from './components/Partners.vue';
import AboutUs from './components/AboutUs.vue';

export default defineComponent({
  components: {
    Slider,
    Skills,
    Services,
    Projects,
    Clients,
    Partners,
    AboutUs,
  },
});
</script>
