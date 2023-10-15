<template>
  <HeaderSection />
  <PhotoTextSection :data="aboutMeData" />
  <ServicesSection />
  <PhotoTextSection :data="portfolioData" />
  <CustomerSection />
  <FooterSection />
</template>

<script>

import PhotoTextSection from '@/components/Sections/PhotoTextSection.vue';
import HeaderSection from '@/components/Sections/HeaderSection.vue';
import ServicesSection from '@/components/Sections/ServicesSection.vue';
import CustomerSection from '@/components/Sections/CustomerSection.vue';
import FooterSection from '@/components/Sections/FooterSection.vue';

export default {
  name: 'HomeView',
  components: {
    PhotoTextSection,
    HeaderSection,
    ServicesSection,
    CustomerSection,
    FooterSection
  },
  data(){
    return {
      aboutMeData: {
        title: "About Me",
        description: "I have over a decade of experience in the field of marketing, starting my career as a junior content writer and gradually working my way up to become a seasoned marketing consultant. My expertise lies in crafting comprehensive digital marketing strategies that drive results",
        awards: true,
        image: "jdoephoto",
        layout: "image-last"
      },
      portfolioData: {
        title: "Portfolio",
        description: "In my portfolio of projects, I've had the privilege of collaborating with a diverse range of clients across various industries. Each project is a testament to my commitment to delivering results-driven solutions.",
        awards: false,
        image: "projectsphoto",
        layout: "image-first"
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  @import "@/assets/global.scss";
</style>
