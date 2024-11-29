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
    setup() {
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
            modules: [Navigation, Pagination, A11y],
        };
    },
};
</script>

<template>
    <swiper :modules="modules" :slides-per-view="1" :space-between="50" navigation :pagination="{ clickable: true }"
        :scrollbar="{ draggable: true }" @swiper="onSwiper" @slideChange="onSlideChange">
        <swiper-slide v-for="slide in slides" :key="slide">{{ slide }}</swiper-slide>
    </swiper>

    <div class="flex justify-center gap-4">
        <button @click="slidePrev" class="bg-blue-500 text-white px-4 py-2 rounded">Previous Slide</button>
        <button @click="slideNext" class="bg-blue-500 text-white px-4 py-2 rounded">Next Slide</button>
    </div>
</template>



<style lang="scss" scoped></style>