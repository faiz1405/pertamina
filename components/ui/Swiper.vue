<script>
import { Navigation, Pagination, A11y } from 'swiper/modules';
import { Swiper, SwiperSlide } from 'swiper/vue';
import NextSlide from '/img/tumb-slide-2-1.png'


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
            imageLoadingStates,
            handleImageLoad,
            NextSlide
        };
    },
};
</script>

<template>
    <div class="relative">
        <swiper :modules="modules" :slides-per-view="1" :space-between="50" :pagination="{ clickable: true }"
            :scrollbar="{ draggable: true }" @swiper="onSwiper" @slideChange="onSlideChange">
            <swiper-slide v-for="(slide, index) in slides" :key="index">
                <NuxtImg :src="slide" format="webp" class="w-full" quality="100" @load="handleImageLoad(index)"
                    @error="handleImageError" />
            </swiper-slide>
        </swiper>

        <button @click="slideNext"
            class="absolute top-[15%] left-[85%]  translate-x-[-50%] translate-y-[-50%] z-10 width ">
            <div class="relative tumb">
                <div class="wrapper-tumb">
                    <NuxtImg :src="NextSlide" format="webp" class="w-full" alt="logo pertamina" />
                    <div class="pulse">
                        <i></i>
                        <i></i>
                        <i></i>
                        <i></i>
                        <i></i>
                    </div>
                    <div
                        class="absolute top-1/2 left-1/2  translate-x-[-50%] translate-y-[-50%] w-[250px] text-tumb text-left">
                        <p class="text-white">Upcoming Pages</p>
                        <h2 class="font-semibold text-white">Bahan Bakar Minyak (BBM) Satu Harga (Slide 2)</h2>
                    </div>
                </div>
            </div>



        </button>

        <NuxtLink to="/"
            class="absolute top-[98%] left-[15%] translate-x-[-50%] translate-y-[-50%] z-10 text-[#026FC2] py-2 px-4 text-xl flex items-center rounded-full bg-white">
            <svg xmlns="http://www.w3.org/2000/svg" class="text-[#026FC2;]" width="32" height="32" viewBox="0 0 32 32"
                fill="#026FC2">
                <path d="M6.6666 16L25.3333 16M6.6666 16L14.6666 8M6.6666 16L14.6666 24" stroke="#026FC2"
                    stroke-width="2.66667" stroke-linecap="round" stroke-linejoin="round" />
            </svg>
            Back to Home
        </NuxtLink>
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

  .wrapper-tumb{
    position: absolute;
    display: contents;
    z-index: 999;
  }

  .wrapper-tumb:hover .text-tumb{
    opacity: 1;
    transform: translate(-350px, -40px) 
  }

  .width:hover .tumb::before{
  
    opacity: 1; /* Makes it visible */
    left: -48px;
}

  .text-tumb{
    opacity: 0;
    transition: all 0.3s ease-in-out;
  }

  

  .pulse{
    position: absolute;
    top: 50%;
    left: 50%;
    z-index: -5;
  }

  .pulse i{
    position: absolute;
    top: 50%;
    left: 50%;
    width: 50px;
    height: 50px;
    margin-top: -25px;
    margin-left: -25px;
    border: 1.5px solid white;
    border-radius: 50%;
    animation: pulsed 3600ms ease-out 1s infinite;
    opacity: 0;
}

.pulse i:nth-child(2) {
    animation-delay: 1300ms;
  
}

.pulse i:nth-child(3) {
    animation-delay: 1600ms;
}

.pulse i:nth-child(4) {
    animation-delay: 1900ms;
}

.pulse i:nth-child(5) {
    animation-delay: 2200ms;
}

.tumb::before{
    content: "";
    position: absolute;
    top: 50%;
    left: 50%;
    width: 50px;
    height: 3px;
    background: white;
    opacity: 0;
    transform: translateY(-50%); /* Ensure alignment at 50% height */
    transition: all 0.3s ease-in-out; /* Enables transition for width and opacity */
    
}

@keyframes pulsed {
    0% {
        transform: scale(0);
        opacity: 1;
    }
    50% {
        transform: scale(3);
        opacity: 0;
    }
    100% {
        opacity: 0;
    }
}

@keyframes reveal {
  from {
    clip-path: inset(0 0 0 100%);
  }
  to {
    clip-path: inset(0 0 0 0);
  }
}

</style>