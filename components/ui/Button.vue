<template>
    <NuxtLink :to="link" class="btn-custom">
        <slot />
    </NuxtLink>
</template>

<script setup>
defineProps({
    text: {
        type: String,
        required: true
    },
    link: {
        type: String,
        required: true
    }
})
</script>

<style scoped>
.btn-custom{
    color: #FFF;
    padding: 10px 20px;
    border-radius: 10.295px;
    border: 1.287px solid #FFF;
    background: radial-gradient(100% 100% at 50% 0%, rgba(255, 255, 255, 0.30) 0%, rgba(255, 255, 255, 0.00) 100%), linear-gradient(94deg, #66B7C0 1.69%, #66B7C0 10.23%, #8AC6EC 54%, #66B7C0 91.36%, #66B7C0 99.83%);
}</style>