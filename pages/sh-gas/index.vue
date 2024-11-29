<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>


<template>
    <div>
        <h1>Sh Gas Page</h1>

        <Swiper :slides="['Slide sh-gas 1 ', 'Slide sh-gas 2', 'Slide sh-gas 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style lang="scss" scoped></style>