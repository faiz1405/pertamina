<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>

<template>
    <div>
        <h1>Sh pnre</h1>

        <Swiper :slides="['Slide pnre 1 ', 'Slide pnre 2', 'Slide pnre 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>