<script setup>
import { ref } from 'vue';
import HeroSection from '@/components/HeroSection.vue';
import FooterSection from '@/components/FooterSection.vue';
import TechStack from '@/components/TechStack.vue';
import PortifolioSection from '@/components/PortifolioSection.vue';
import AboutMe from '@/components/AboutMe.vue';
//import DepoimentsSection from '@/components/DepoimentsSection.vue';
import CTA from '@/components/CTA.vue';

// Importando a imagem diretamente
import profilePicture from '@/assets/profile_picture.png';

const heroSectionProps = ref({
  title: 'Luiz Trindade',
  description: 'Desenvolvedor Full Stack com experiência em Vue.js, Node.js e outras tecnologias modernas. Apaixonado por criar soluções inovadoras, eficientes e escaláveis para a web.',
  backgroundImage: 'https://wallpaperaccess.com/full/314785.jpg',
  profileImage: profilePicture
});

const aboutMeProps = ref({
  title: 'Sobre Mim',
  description: 'Sou um desenvolvedor dedicado com paixão por transformar ideias em realidade digital. Com experiência em diversas tecnologias, busco sempre entregar soluções de alta qualidade que atendam às necessidades dos usuários.',
  backgroundImage: 'https://img.daisyui.com/images/stock/photo-1507358522600-9f71e620c44e.webp',
  profileImage: profilePicture
});
</script>


<template>
  <div class="space-y-8">
    <HeroSection v-bind="heroSectionProps" />

    <TechStack />

    <PortifolioSection />

    <AboutMe v-bind="aboutMeProps" />

    <!--
  
    <DepoimentsSection />
    -->

    <CTA />

    <FooterSection />
  </div>
</template>

<style scoped></style>
