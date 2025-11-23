<script setup>
import { ref } from 'vue';
import HeroSection from '@/components/HeroSection.vue';
import FooterSection from '@/components/FooterSection.vue';
import PriceSection from '@/components/PricingCard.vue';
import TechStack from '@/components/TechStack.vue';
import PortifolioSection from '@/components/PortifolioSection.vue';
import AboutMe from '@/components/AboutMe.vue';
import DepoimentsSection from '@/components/DepoimentsSection.vue';
import CTA from '@/components/CTA.vue';

const heroSectionProps = ref({
  title: 'Luiz Trindade',
  description: 'Desenvolvedor Full Stack com experiência em Vue.js, Node.js e outras tecnologias modernas. Apaixonado por criar soluções inovadoras, eficientes e escaláveis para a web.',
  backgroundImage: 'https://wallpaperaccess.com/full/314785.jpg',
  profileImage: new URL('@/assets/profile_picture.png', import.meta.url).href
});
</script>

<template>
  <div class="space-y-8">
    <HeroSection v-bind="heroSectionProps" />

    <TechStack />

    <PortifolioSection />

    <AboutMe />

    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4 justify-items-center items-center min-h-[50vh]">
      <PriceSection />
      <PriceSection />
      <PriceSection />
    </div>

    <DepoimentsSection />

    <CTA />

    <FooterSection />
  </div>
</template>

<style scoped></style>
