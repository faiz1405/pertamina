<script setup>
import Swiper from '../../components/ui/Swiper.vue'
import ImageSlide1 from '/img/slide-1.webp'
import ImageSlide2 from '/img/slide-2.webp'

const isLoading = ref(true); // Tracks if the images are loading

const handleLoadingComplete = () => {
    isLoading.value = false; // Turn off the loader when images finish loading
};
</script>


<template>
    <div>
        <!-- Loader -->
        <div v-if="isLoading" class="loader">
            Loading slides...
        </div>


        <Swiper :slides="[ImageSlide1, ImageSlide2]" @loading-complete="handleLoadingComplete" />

        <UiButton to="/">
            Back to Home
        </UiButton>
    </div>
</template>

<style scoped>
.loader {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    font-size: 18px;
    color: #666;
}
</style>