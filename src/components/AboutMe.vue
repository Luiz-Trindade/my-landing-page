<script setup>
defineProps({
    title: {
        type: String,
        default: 'Hello there'
    },
    description: {
        type: String,
        default: 'This is a simple hero section description to showcase the component.'
    },
    backgroundImage: {
        type: String,
        default: 'https://img.daisyui.com/images/stock/photo-1507358522600-9f71e620c44e.webp'
    },
    profileImage: {
        type: String,
        default: 'https://img.daisyui.com/images/stock/photo-1635805737707-575885ab0820.webp'
    }
});
</script>

<template>
    <div class="hero bg-base-200 min-h-[80vh]" :style="`background-image: url(${backgroundImage});`">
        <div class="hero-overlay bg-opacity-60 backdrop-blur-md"></div>
        <div class="hero-content flex flex-col-reverse lg:flex-row text-neutral-content gap-6 p-4">
            <div class="text-center lg:text-left">
                <h1
                    class="text-4xl lg:text-7xl break-words font-extrabold bg-clip-text text-transparent bg-gradient-to-r from-green-400 to-blue-500">
                    {{ title }}
                </h1>
                <p class="py-4 text-lg lg:text-xl font-bold break-words max-w-full lg:max-w-lg">
                    {{ description }}
                </p>
                <div class="flex justify-center lg:justify-center">
                    <button class="btn btn-primary">Entrar em contato</button>
                </div>
            </div>
            <div class="avatar flex justify-center">
                <div
                    class="w-32 lg:w-64 rounded-full ring ring-success ring-offset-base-100 ring-offset-4 shadow-[0_0_20px_5px_rgba(34,197,94,0.7)]">
                    <img :src="profileImage" />
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped></style>