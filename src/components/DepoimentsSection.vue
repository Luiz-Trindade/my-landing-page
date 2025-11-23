<script setup>
const testimonials = [
    {
        id: 1,
        name: "João Silva",
        text: "Este produto mudou minha vida! Recomendo para todos.",
        avatar: "https://img.daisyui.com/images/profile/demo/yellingcat@192.webp",
    },
    {
        id: 2,
        name: "Maria Oliveira",
        text: "Excelente qualidade e atendimento. Estou muito satisfeita!",
        avatar: "https://img.daisyui.com/images/profile/demo/yellingcat@192.webp",
    },
    {
        id: 3,
        name: "Carlos Pereira",
        text: "Superou minhas expectativas. Voltarei a comprar com certeza.",
        avatar: "https://img.daisyui.com/images/profile/demo/yellingcat@192.webp",
    },
    {
        id: 4,
        name: "Ana Costa",
        text: "Entrega rápida e produto impecável. Parabéns à equipe!",
        avatar: "https://img.daisyui.com/images/profile/demo/yellingcat@192.webp",
    },
];
</script>

<template>
    <div class="container mx-auto px-4 py-8">
        <h1 class="text-3xl font-bold text-center mb-8">Depoimentos</h1>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            <div v-for="testimonial in testimonials" :key="testimonial.id" class="card w-full bg-base-100 shadow-md">
                <div class="card-body">
                    <div class="flex items-center mb-4">
                        <div class="avatar">
                            <div class="w-12 rounded-full">
                                <img :src="testimonial.avatar" alt="Avatar" />
                            </div>
                        </div>
                        <h2 class="card-title ml-4">{{ testimonial.name }}</h2>
                    </div>
                    <p>{{ testimonial.text }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.container {
    max-width: 1200px;
}
</style>
