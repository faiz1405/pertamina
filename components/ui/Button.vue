<template>
    <NuxtLink :to="link" class="w-[250px] text-center px-6 py-3 transition-all bg-transparent border-2 rounded-lg"
        :class="typeButton(type)">
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
    },
    type: {
        type: String,
        required: false
    }
})

function typeButton(type) {
    if (type === 'blue') {
        return 'border-cyan-400 text-cyan-400 hover:bg-cyan-500 hover:text-white'
    } else if (type === 'gold') {
        return 'text-yellow-400 border-yellow-400 rounded-lg hover:bg-yellow-500 hover:text-white'
    } else if (type === 'gray') {
        return 'text-gray-400 border-gray-400 rounded-lg hover:bg-gray-500 hover:text-white h-[100px] flex justify-center items-center'
    }
}
</script>

<style scoped>
.btn-custom{
    color: #FFF;
    padding: 10px 20px;
    border-radius: 10.295px;
    border: 1.287px solid #FFF;
    background: radial-gradient(100% 100% at 50% 0%, rgba(255, 255, 255, 0.30) 0%, rgba(255, 255, 255, 0.00) 100%), linear-gradient(94deg, #66B7C0 1.69%, #66B7C0 10.23%, #8AC6EC 54%, #66B7C0 91.36%, #66B7C0 99.83%);
}</style>