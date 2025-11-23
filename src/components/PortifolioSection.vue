<script setup>
import Hover3D from '@/components/Hover3D.vue';

// Dados dos projetos (Simulando um portfólio real)
const projects = [
    {
        title: "E-commerce Dashboard",
        description: "Painel administrativo completo para gestão de vendas e estoque com gráficos em tempo real.",
        image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fstorage.googleapis.com%2Ftda-website%2F2023%2F01%2Fshowing-cart-trolley-shopping-online-sign-graphic-scaled.jpg&f=1&nofb=1&ipt=7917cad28f2b15a19624a2a3dec76ff71868747b48f37be3c47cf66fc3ef79e7", // Substitua por print real
        techs: ["Vue.js", "Tailwind", "Chart.js"],
        demoLink: "#",
        repoLink: "#"
    },
    {
        title: "App de Delivery",
        description: "Aplicação web progressiva (PWA) para pedidos de comida com geolocalização.",
        image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Funblast.com%2Fwp-content%2Fuploads%2F2021%2F07%2FFood-Delivery-App-Template-1600x1200.jpg&f=1&nofb=1&ipt=5a2572fd3056fb2026fe5ff6ce8e2eb1e60adabcdddfede1dfd867619ea87145",
        techs: ["Nuxt 3", "Firebase", "Pinia"],
        demoLink: "#",
        repoLink: "#"
    },
    {
        title: "Landing Page SaaS",
        description: "Página de alta conversão otimizada para SEO e performance (Lighthouse 100%).",
        image: "https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Fs3-alpha.figma.com%2Fhub%2Ffile%2F3542318799%2Fffd9d4d0-d341-4c1f-a2f2-cbe9e0c9b7d2-cover.png&f=1&nofb=1&ipt=745bb651383b9d97c03ba8b7213a3e0d105db53ce6cdd50295065b5adcd76cfa",
        techs: ["Vue 3", "Vite", "DaisyUI"],
        demoLink: "#",
        repoLink: "#"
    }
];
</script>

<template>
    <section class="py-12 px-4">
        <div class="flex flex-col items-center text-center mb-16 gap-4 pb-8">
            <h1 class="w-full text-center text-4xl font-bold text-white mb-2">Meus Projetos Recentes</h1>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 max-w-7xl mx-auto">
            <div v-for="(project, index) in projects" :key="index"
                class="card bg-base-100 shadow-xl hover:shadow-2xl transition-shadow duration-300 border border-base-200">

                <figure class="px-4 pt-4 cursor-pointer overflow-visible z-10">
                    <Hover3D :src="project.image" :alt="project.title"
                        customClass="rounded-xl w-full h-48 object-cover shadow-md" />
                </figure>

                <div class="card-body">
                    <h3 class="card-title font-bold text-2xl">
                        {{ project.title }}
                    </h3>

                    <p class="text-sm text-base-content/70 mt-2">
                        {{ project.description }}
                    </p>

                    <div class="flex flex-wrap gap-2 mt-4">
                        <span v-for="tech in project.techs" :key="tech"
                            class="badge badge-outline badge-primary badge-sm">
                            {{ tech }}
                        </span>
                    </div>

                    <div class="card-actions justify-end mt-6 items-center">
                        <a :href="project.repoLink" class="btn btn-ghost btn-sm gap-2">
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24"
                                fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round">
                                <path
                                    d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22">
                                </path>
                            </svg>
                            Código
                        </a>
                        <a :href="project.demoLink" class="btn btn-primary btn-sm gap-2">
                            Ver Demo
                            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 24 24"
                                fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                stroke-linejoin="round">
                                <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                                <polyline points="15 3 21 3 21 9"></polyline>
                                <line x1="10" y1="14" x2="21" y2="3"></line>
                            </svg>
                        </a>
                    </div>
                </div>
            </div>

        </div>
    </section>
</template>

<style scoped>
/* Opcional: Ajuste fino se o Hover3D estiver cortando */
figure {
    perspective: 1000px;
}
</style>