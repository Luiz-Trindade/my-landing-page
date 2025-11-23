<script setup>
import Hover3D from '@/components/Hover3D.vue';

// Exemplo de stacks (substitua pelos seus dados reais)
const stacks = [
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original-wordmark.svg",
        alt: "Vue.js",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nuxt/nuxt-original-wordmark.svg",
        alt: "Nuxt.js",
        customClass: "w-40",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuetify/vuetify-original.svg",
        alt: "Vuetify",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg",
        alt: "Python",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original.svg",
        alt: "FastAPI",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original-wordmark.svg",
        alt: "Docker",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original-wordmark.svg",
        alt: "Redis",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original-wordmark.svg",
        alt: "PostgreSQL",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg",
        alt: "MySQL",
        customClass: "w-40",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/ionic/ionic-original-wordmark.svg",
        alt: "Ionic",
        customClass: "w-60",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/capacitor/capacitor-original.svg",
        alt: "Capacitor",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg",
        alt: "JavaScript",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linux/linux-original.svg",
        alt: "Linux",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/android/android-original.svg",
        alt: "Android",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nginx/nginx-original.svg",
        alt: "Nginx",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bun/bun-original.svg",
        alt: "Bun",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/go/go-original.svg",
        alt: "Go",
        customClass: "w-30",
    },
    {
        src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original-wordmark.svg",
        alt: "GitHub",
        customClass: "w-30",
    }
];
</script>

<template>
    <div
        class="flex flex-wrap justify-center items-center min-h-[50vh] gap-6 p-6 bg-gradient-to-b from-gray-700 to-gray-800 shadow-lg">
        <h1 class="w-full text-center text-4xl font-bold text-white mb-2">Minhas Ferramentas de Trabalho</h1>

        <Hover3D v-for="(stack, index) in stacks" :key="index" :src="stack.src" :alt="stack.alt"
            :customClass="stack.customClass" class="hover:scale-105 transition-transform duration-300 ease-out" />
    </div>
</template>

<style scoped>
/* Adicione estilos adicionais aqui, se necessário */
</style>