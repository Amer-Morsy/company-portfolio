<template>
  <div class="footer">
    <SectionTitle :title="t('footer.header')" />

    <div class="footer-container">
      <div class="bio">
        <div class="logo-container">
          <img :src="imgLogo" />
        </div>
        <p class="text">{{ t('footer.bio') }}</p>

        <ul v-if="socialMediaList" class="social-media">
          <template v-for="(social, index) in socialMediaList" :key="index">
            <li>
              <a :href="social.link" target="_blank" :title="social.title">
                <img :src="social.image" />
              </a>
            </li>
          </template>
        </ul>
      </div>

      <div class="location">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d19549.964374530697!2d31.161375574989783!3d29.980059509806985!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x145845464c6dc685%3A0xeb3d6cd29c15b77e!2sAdmins-Egypt!5e0!3m2!1sen!2seg!4v1658944826311!5m2!1sen!2seg"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>

      <div class="contact-data">
        <template v-if="contactDataList">
          <template v-for="(item, index) in contactDataList" :key="index">
            <div class="item">
              <div class="title">
                <img :src="item.image" />
                <span class="text">{{ item.title }}</span>
              </div>
              <ul>
                <template v-if="item.list">
                  <li
                    v-for="(itemList, indexList) in item.list"
                    :key="indexList"
                    :class="item.phoneNumber ? 'phone-number' : ''"
                  >
                    {{ itemList }}
                  </li>
                </template>
              </ul>
            </div>
          </template>
        </template>
      </div>
    </div>

    <CustomDivider />
    <div class="copyright">
      <span class="copyright-text">{{ t('footer.copyRight') }}</span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useI18n } from 'vue-i18n';
import SocialMedia from './../types/SocialMedia';
import ContactData from './../types/ContactData';
import SectionTitle from './SectionTitle.vue';
import CustomDivider from './CustomDivider.vue';
import {
  imgLogo,
  imgAddress,
  imgPhone,
  imgMail,
  imgSocialMediaFacebook,
  imgSocialMediaWhatsapp,
  imgSocialMediaYoutube,
  imgSocialMediaLinkedin,
  imgSocialMediaTwitter,
} from './../utils/images';

export default defineComponent({
  components: { SectionTitle, CustomDivider },
  setup() {
    const { t } = useI18n();
    const contactDataList: ContactData[] = [
      {
        title: t('footer.contactData.address'),
        list: [t('footer.contactData.address1')],
        image: imgAddress,
        phoneNumber: false,
      },
      {
        title: t('footer.contactData.phone'),
        list: [t('footer.contactData.phone1')],
        image: imgPhone,
        phoneNumber: true,
      },
      {
        title: t('footer.contactData.mail'),
        list: [t('footer.contactData.mail1')],
        image: imgMail,
        phoneNumber: false,
      },
    ];
    const socialMediaList: SocialMedia[] = [
      {
        title: t('footer.socialMedia.faceBook'),
        link: 'https://www.facebook.com/AdminsSystems',
        image: imgSocialMediaFacebook,
      },
      {
        title: t('footer.socialMedia.whatsApp'),
        link: 'https://api.whatsapp.com/send?phone=201208080847',
        image: imgSocialMediaWhatsapp,
      },
      {
        title: t('footer.socialMedia.youTube'),
        link: 'https://www.youtube.com/channel/UCxeh_kVUtUCzu2lxgo30vWA',
        image: imgSocialMediaYoutube,
      },
      {
        title: t('footer.socialMedia.linkedIn'),
        link: 'https://www.linkedin.com/company/admins-egypt/',
        image: imgSocialMediaLinkedin,
      },
      {
        title: t('footer.socialMedia.twitter'),
        link: 'https://www.facebook.com/AdminsSystems',
        image: imgSocialMediaTwitter,
      },
    ];

    return { t, imgLogo, contactDataList, socialMediaList };
  },
});
</script>

<style lang="scss" scoped>
@import '@/assets/styles/footer.scss';
</style>
