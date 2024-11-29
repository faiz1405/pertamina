<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>

<template>
    <div>
        <h1>Bina Medika Page</h1>

        <Swiper :slides="['Slide bina 1 ', 'Slide bina 2', 'Slide bina 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>



<style lang="scss" scoped></style>