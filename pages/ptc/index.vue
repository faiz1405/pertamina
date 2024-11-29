<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>


<template>
    <div>
        <h1>ptc Page</h1>

        <Swiper :slides="['Slide ptc 1 ', 'Slide ptc 2', 'Slide ptc 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>