<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>

<template>
    <div>
        <h1>Sh iml Page</h1>

        <Swiper :slides="['Slide sh-iml 1 ', 'Slide sh-iml 2', 'Slide sh-iml 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>