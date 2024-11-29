<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>


<template>
    <div>
        <h1>Sh c&t Page</h1>

        <Swiper :slides="['Slide cnt 1 ', 'Slide cnt 2', 'Slide cnt 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>