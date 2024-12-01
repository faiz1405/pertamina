<script>
import { Navigation, Pagination, A11y } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue';


import 'swiper/css';
import 'swiper/css/navigation';
import 'swiper/css/pagination';

export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    props: {
        slides: Array,
    },
    setup(props, { emit }) {
        const imageLoadingStates = ref(props.slides.map(() => true)); // Tracks loading state for each image

        const handleImageLoad = (index) => {
            imageLoadingStates.value[index] = false;

            // Check if all images are loaded
            if (!imageLoadingStates.value.includes(true)) {
                emit('loading-complete'); // Notify parent that loading is complete
            }
        };

        let swiperInstance = null;

        const onSwiper = (swiper) => {
            swiperInstance = swiper;
            console.log('Swiper instance:', swiperInstance);
        };

        const onSlideChange = () => {
            console.log('Slide changed');
        };

        const slidePrev = () => {
            if (swiperInstance) swiperInstance.slidePrev();
        };

        const slideNext = () => {
            if (swiperInstance) swiperInstance.slideNext();
        };




        return {
            onSwiper,
            onSlideChange,
            slidePrev,
            slideNext,
            modules: [Navigation, Pagination, A11y], imageLoadingStates,
            handleImageLoad,
        };
    },
};
</script>

<template>
    <div>
        <swiper :modules="modules" :slides-per-view="1" :space-between="50" navigation :pagination="{ clickable: true }"
            :scrollbar="{ draggable: true }" @swiper="onSwiper" @slideChange="onSlideChange">
            <swiper-slide v-for="(slide, index) in slides" :key="index">
                <NuxtImg :src="slide" format="webp" class="w-full" quality="100" @load="handleImageLoad(index)"
                    @error="handleImageError" />
            </swiper-slide>
        </swiper>
        <div class="flex justify-center gap-4">
            <button @click="slidePrev" class="px-4 py-2 text-white bg-blue-500 rounded">Previous Slide</button>
            <button @click="slideNext" class="px-4 py-2 text-white bg-blue-500 rounded">Next Slide</button>
        </div>
    </div>
</template>



<style scoped>
.loader {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 16px;
    color: #fff;
    background: rgba(0, 0, 0, 0.6);
    padding: 10px 20px;
    border-radius: 5px;
    z-index: 10;
    width: max-content;
    height: max-content;
    z-index: 9999;
  }
</style>