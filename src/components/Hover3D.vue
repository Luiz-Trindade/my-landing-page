<script setup>
defineProps({
    src: {
        type: String,
        required: true
    },
    alt: {
        type: String,
        default: '3D card'
    },
    customClass: {
        type: String,
        default: ''
    }
});
</script>

<template>
    <div :class="`hover-3d ${customClass}`">
        <!-- content -->
        <figure class="max-w-100 rounded-2xl">
            <img :src="src" :alt="alt" />
        </figure>
        <!-- 8 empty divs needed for the 3D effect -->
        <div v-for="n in 8" :key="n"></div>
    </div>
</template>

<style scoped></style>
