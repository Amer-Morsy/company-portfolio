<template>
  <div class="about">
    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <div class="text-center my-3">
      <b-button>GetUserAppSettingDetails</b-button>
    </div>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>

    <h1>This is an about page</h1>
    <h3>{{ t('general.projectName') }}</h3>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';

export default defineComponent({
  setup() {
    const { t } = useI18n();

    return { t };
  },
});
</script>
