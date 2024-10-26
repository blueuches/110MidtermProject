<template>
  <v-app>
    <PageHeader />
    <v-main>
      <IntroSection />
      <AboutSection />
      <PortfolioSection />
      <ServiceSection />
      <ContactSection />
    </v-main>
    <PageFooter />
  </v-app>
</template>

<script>
import PageHeader from './components/PageHeader.vue'
import IntroSection from './components/IntroSection.vue'
import AboutSection from './components/AboutSection.vue'
import PortfolioSection from './components/PortfolioSection.vue'
import ServiceSection from './components/ServiceSection.vue'
import ContactSection from './components/ContactSection.vue'
import PageFooter from './components/PageFooter.vue'

export default {
  name: 'App',
  components: {
    PageHeader,
    IntroSection,
    AboutSection,
    PortfolioSection,
    ServiceSection,
    ContactSection,
    PageFooter,
  }
}
</script>

<style>
@import url('https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css');

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Garamond;
}

</style>