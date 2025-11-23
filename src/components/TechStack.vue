<script setup>
import { ref, computed } from 'vue';
import Hover3D from '@/components/Hover3D.vue';

const stacks = [
    { id: 'vue', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuejs/vuejs-original-wordmark.svg", alt: "Vue.js", category: "frontend" },
    { id: 'nuxt', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nuxt/nuxt-original-wordmark.svg", alt: "Nuxt.js", category: "frontend" },
    { id: 'vuetify', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/vuetify/vuetify-original.svg", alt: "Vuetify", category: "frontend" },
    { id: 'javascript', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg", alt: "JavaScript", category: "frontend" },
    { id: 'python', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg", alt: "Python", category: "backend" },
    { id: 'fastapi', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/fastapi/fastapi-original.svg", alt: "FastAPI", category: "backend" },
    { id: 'go', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/go/go-original.svg", alt: "Go", category: "backend" },
    { id: 'bun', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/bun/bun-original.svg", alt: "Bun", category: "backend" },
    { id: 'postgresql', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/postgresql/postgresql-original-wordmark.svg", alt: "PostgreSQL", category: "backend" },
    { id: 'mysql', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/mysql/mysql-original-wordmark.svg", alt: "MySQL", category: "backend" },
    { id: 'redis', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redis/redis-original-wordmark.svg", alt: "Redis", category: "backend" },
    { id: 'ionic', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/ionic/ionic-original-wordmark.svg", alt: "Ionic", category: "mobile" },
    { id: 'capacitor', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/capacitor/capacitor-original.svg", alt: "Capacitor", category: "mobile" },
    { id: 'android', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/android/android-original.svg", alt: "Android", category: "mobile" },
    { id: 'docker', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original-wordmark.svg", alt: "Docker", category: "devops" },
    { id: 'linux', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/linux/linux-original.svg", alt: "Linux", category: "devops" },
    { id: 'github', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original-wordmark.svg", alt: "GitHub", category: "devops" },
    { id: 'nginx', src: "https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/nginx/nginx-original.svg", alt: "Nginx", category: "production" }
];

const services = [
    { id: 1, name: 'Landing Page', icon: '🌐', stacks: ['vue', 'javascript', 'nuxt'], price: 1500, category: 'Web' },
    { id: 2, name: 'Aplicação Web Completa', icon: '💻', stacks: ['vue', 'nuxt', 'vuetify', 'javascript', 'python', 'fastapi', 'postgresql', 'mysql', 'docker'], price: 5000, category: 'Web' },
    { id: 3, name: 'API REST', icon: '🔌', stacks: ['python', 'fastapi', 'postgresql', 'mysql', 'redis', 'docker'], price: 3000, category: 'Backend' },
    { id: 4, name: 'API Go (Alta Performance)', icon: '⚡', stacks: ['go', 'postgresql', 'mysql', 'redis', 'docker'], price: 4000, category: 'Backend' },
    { id: 5, name: 'App Android', icon: '📱', stacks: ['ionic', 'capacitor', 'vue', 'javascript', 'android'], price: 4500, category: 'Mobile' },
    { id: 6, name: 'App Cross-Platform', icon: '📲', stacks: ['ionic', 'capacitor', 'vue', 'javascript', 'android'], price: 5000, category: 'Mobile' },
    { id: 7, name: 'E-commerce', icon: '🛒', stacks: ['vue', 'nuxt', 'vuetify', 'python', 'fastapi', 'postgresql', 'mysql', 'redis', 'docker', 'nginx'], price: 5000, category: 'Web' },
    { id: 8, name: 'Dashboard Administrativo', icon: '📊', stacks: ['vue', 'nuxt', 'vuetify', 'javascript', 'python', 'fastapi', 'postgresql', 'mysql'], price: 4000, category: 'Web' },
    { id: 9, name: 'Microserviços', icon: '🏗️', stacks: ['python', 'fastapi', 'go', 'docker', 'redis', 'postgresql', 'mysql', 'nginx', 'linux'], price: 5000, category: 'Backend' },
    { id: 10, name: 'Deploy e Infraestrutura', icon: '🚀', stacks: ['docker', 'linux', 'nginx', 'github'], price: 2000, category: 'DevOps' },
    { id: 11, name: 'Chatbot com IA', icon: '🤖', stacks: ['python', 'fastapi', 'redis', 'postgresql', 'mysql', 'docker'], price: 4000, category: 'AI' },
    { id: 12, name: 'CMS Personalizado', icon: '📝', stacks: ['vue', 'nuxt', 'vuetify', 'python', 'fastapi', 'postgresql', 'mysql', 'docker'], price: 4500, category: 'Web' },
    { id: 13, name: 'PWA', icon: '📱', stacks: ['vue', 'nuxt', 'javascript', 'python', 'fastapi'], price: 3500, category: 'Web' },
    { id: 14, name: 'Sistema Tempo Real', icon: '⚡', stacks: ['vue', 'javascript', 'python', 'fastapi', 'redis', 'postgresql', 'mysql'], price: 4000, category: 'Backend' },
    { id: 15, name: 'Aplicação Frontend Genérica', icon: '🖼️', stacks: ['vue', 'nuxt', 'vuetify', 'javascript'], price: 3000, category: 'Web' },
    { id: 16, name: 'Aplicação Backend Genérica', icon: '🔧', stacks: ['python', 'fastapi', 'postgresql', 'mysql', 'docker'], price: 3500, category: 'Backend' }
];

const categories = ['Todos', 'Web', 'Backend', 'Mobile', 'DevOps', 'AI'];
const activeCategory = ref('Todos');
const selectedService = ref(null);
const currentPage = ref(1);
const itemsPerPage = 6;

const filteredServices = computed(() =>
    activeCategory.value === 'Todos'
        ? services
        : services.filter(s => s.category === activeCategory.value)
);

const totalPages = computed(() => Math.ceil(filteredServices.value.length / itemsPerPage));

const paginatedServices = computed(() => {
    const start = (currentPage.value - 1) * itemsPerPage;
    const end = start + itemsPerPage;
    return filteredServices.value.slice(start, end);
});

const displayStacks = computed(() =>
    selectedService.value
        ? stacks.filter(s => selectedService.value.stacks.includes(s.id))
        : stacks
);

const formatPrice = (price) => price.toLocaleString('pt-BR', { style: 'currency', currency: 'BRL' });

const goToPage = (page) => {
    currentPage.value = page;
};
</script>

<template>
    <div class="min-h-screen bg-gradient-to-br from-base-300 via-base-200 to-base-300 p-4 md:p-8">
        <div class="max-w-7xl mx-auto">
            <!-- Header -->
            <div class="text-center mb-6">
                <h1 class="text-4xl md:text-5xl font-bold mb-2">Serviços de Desenvolvimento</h1>
            </div>
            <br>

            <!-- Tabs de Categorias -->
            <div role="tablist" class="tabs tabs-boxed max-w-2xl mx-auto bg-base-100 p-2 mb-6 rounded-lg">
                <a v-for="cat in categories" :key="cat" role="tab" class="tab"
                    :class="{ 'tab-active': activeCategory === cat }"
                    @click="activeCategory = cat; selectedService = null; currentPage = 1">
                    <span :class="{ 'font-bold': activeCategory === cat }">{{ cat }}</span>
                </a>
            </div>
            <br>

            <!-- Layout 2 Colunas -->
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-6">

                <!-- Coluna Esquerda: Serviços -->
                <div class="flex flex-col gap-4">
                    <div class="card bg-base-100 shadow-xl min-h-[600px]">
                        <div class="card-body">
                            <h2 class="card-title text-2xl mb-4">Serviços Disponíveis</h2>

                            <!-- Grid de Serviços -->
                            <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mb-4">
                                <div v-for="service in paginatedServices" :key="service.id"
                                    class="card bg-base-200 shadow hover:shadow-lg transition-all duration-300 cursor-pointer"
                                    :class="{ 'ring-2 ring-primary': selectedService?.id === service.id }"
                                    @click="selectedService = service">

                                    <div class="card-body p-4">
                                        <div class="flex items-center gap-2 mb-2">
                                            <span class="text-3xl">{{ service.icon }}</span>
                                            <h3 class="font-bold text-sm">{{ service.name }}</h3>
                                        </div>

                                        <div class="flex justify-between items-center">
                                            <div class="badge badge-outline badge-sm">{{ service.category }}</div>
                                            <div class="badge badge-primary font-bold">
                                                {{ formatPrice(service.price) }}
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>

                            <!-- Pagination -->
                            <div v-if="totalPages > 1" class="join justify-center">
                                <button class="join-item btn btn-sm" :disabled="currentPage === 1"
                                    @click="goToPage(currentPage - 1)">
                                    «
                                </button>
                                <button v-for="page in totalPages" :key="page" class="join-item btn btn-sm"
                                    :class="{ 'btn-active': currentPage === page }" @click="goToPage(page)">
                                    {{ page }}
                                </button>
                                <button class="join-item btn btn-sm" :disabled="currentPage === totalPages"
                                    @click="goToPage(currentPage + 1)">
                                    »
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Info do Serviço Selecionado -->
                    <!--
                    
                    <div v-if="selectedService" class="alert shadow-lg">
                        <div class="flex-1">
                            <span class="text-3xl mr-3">{{ selectedService.icon }}</span>
                            <div>
                                <h3 class="font-bold text-xl">{{ selectedService.name }}</h3>
                                <div class="text-xs mt-1">
                                    {{ displayStacks.length }} tecnologias necessárias • {{
                                        formatPrice(selectedService.price) }}
                                </div>
                            </div>
                        </div>
                        <div class="flex-none">
                            <button class="btn btn-sm btn-circle btn-ghost" @click="selectedService = null">✕</button>
                        </div>
                    </div>
                    -->
                </div>

                <!-- Coluna Direita: Tecnologias -->
                <div class="card bg-base-100 shadow-xl min-h-[600px]">
                    <div class="card-body">
                        <h2 class="card-title text-2xl mb-4">
                            {{ selectedService ? 'Tecnologias Necessárias' : 'Minhas Tecnologias' }}
                        </h2>
                        <div class="flex flex-wrap justify-center gap-6 min-h-[500px] items-center">
                            <TransitionGroup name="tech">
                                <div v-for="stack in displayStacks" :key="stack.id" class="indicator">
                                    <span v-if="selectedService" class="indicator-item badge badge-secondary badge-xs"
                                        :title="stack.alt"></span>
                                    <Hover3D :src="stack.src" :alt="stack.alt" customClass="w-20 h-20"
                                        class="transition-all duration-300" />
                                </div>
                            </TransitionGroup>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </div>
</template>

<style scoped>
.tech-enter-active,
.tech-leave-active {
    transition: all 0.4s ease;
}

.tech-enter-from {
    opacity: 0;
    transform: scale(0.6) rotate(-10deg);
}

.tech-leave-to {
    opacity: 0;
    transform: scale(0.6) rotate(10deg);
}

.tech-move {
    transition: transform 0.4s ease;
}
</style>