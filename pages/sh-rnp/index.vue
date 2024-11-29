<script setup>
import Swiper from '../../components/ui/Swiper.vue'
</script>

<template>
    <div>
        <h1>Sh r&p Page</h1>

        <Swiper :slides="['Slide rnp 1 ', 'Slide rnp 2', 'Slide rnp 3']" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>



<style lang="scss" scoped></style>