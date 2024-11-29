<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>


<template>
    <div>
        <h1>Patrajasa Page</h1>

        <Swiper :slides="['Slide petrajasa 1 ', 'Slide petrajasa 2', 'Slide petrajasa 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>