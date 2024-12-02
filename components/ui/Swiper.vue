<script>
import { EffectCoverflow, Navigation } from "swiper/modules";
import { Swiper, SwiperSlide } from "swiper/vue";

import "swiper/css";
import "swiper/css/pagination";



export default {
    components: {
        Swiper,
        SwiperSlide,
    },
    props: {
        slides: Array,
    },
    setup(props, { emit }) {
        const imageLoadingStates = ref(props.slides.map(() => true));

        const handleImageLoad = (index) => {
            imageLoadingStates.value[index] = false;
            if (!imageLoadingStates.value.includes(true)) {
                emit("loading-complete");
            }
        };

        let swiperInstance = null;

        const onSwiper = (swiper) => {
            swiperInstance = swiper;
            console.log("Swiper instance:", swiperInstance);
        };

        const onSlideChange = () => {
            console.log("Slide changed");
        };

        const slidePrev = () => {
            if (swiperInstance) swiperInstance.slidePrev();
        };

        const slideNext = () => {
            if (swiperInstance) swiperInstance.slideNext();
        };


        return {
            modules: [EffectCoverflow, Navigation],
            onSwiper,
            onSlideChange,
            handleImageLoad,
            slidePrev,
            slideNext
        };
    },
};
</script>



<template>
    <div class="flex items-center h-screen">
        <swiper :modules="modules" :slides-per-view="1" :centered-slides="true" :space-between="10"
            :effect="'coverflow'" :coverflow-effect="{
                rotate: 10,
                stretch: 50,
                depth: 200,
                modifier: 1,
                slideShadows: false
            }" :pagination="{ clickable: true }" navigation @swiper="onSwiper" @slideChange="onSlideChange">
            <swiper-slide v-for="(slide, index) in slides" :key="index" class="custom-slide">
                <NuxtImg :src="slide" format="webp" class="slide-image" quality="100" @load="handleImageLoad(index)"
                    @error="handleImageError" />
            </swiper-slide>
        </swiper>

        <!-- Add navigation buttons -->
        <div @click="slidePrev" class="custom-prev-button"></div>
        <div @click="slideNext" class="custom-next-button"></div>
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



/* General styling for all slides */
.custom-slide {
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.3s ease, filter 0.3s ease, height 0.3s ease, width 0.3s ease; /* Smooth transition */
}

/* Styling for inactive slides (prev/next) */
.swiper-slide:not(.swiper-slide-active) {
  opacity: 0.6;              /* Dim the non-active slides */
  transform: translateX(-50px) scale(0.85);  /* Slightly smaller scale */
  z-index: 9;                /* Ensure they stack behind the active slide */
}

/* Styling for previous slide */
.swiper-slide-prev {
    transform: translateX(35%) !important;
    opacity: 0.8 !important;
}

/* Styling for next slide */
.swiper-slide-next {
    transform: translateX(-35%) !important;
    opacity: 0.8 !important;
}

.swiper-button-next::after, .swiper-button-prev::after {
    content: "" !important;
}

/* Styling for the active slide */
.swiper-slide-active {
  transform: scale(1); /* Full size */
  z-index: 10;         /* Bring to front */
  opacity: 1;          /* Fully visible */
}


/* Back to Home Link */
.back-home-link {
  position: absolute;
  top: 98%;
  left: 15%;
  transform: translate(-50%, -50%);
  z-index: 10;
  text-decoration: none;
  color: #026fc2;
  padding: 8px 16px;
  font-size: 18px;
  display: flex;
  align-items: center;
  border-radius: 24px;
  background-color: #ffffff;
}

/* General styling for all slides */
.custom-slide {
  display: flex;
  justify-content: center;
  align-items: center;
  transition: transform 0.3s ease, filter 0.3s ease, height 0.3s ease; /* Smooth transition for height and other properties */
}

/* Styling for inactive slides */
.swiper-slide:not(.swiper-slide-active) .slide-image {
  height: 65vh; /* Default size for non-active slides */
  filter: blur(4px); /* Add a blur effect */
  opacity: 0.7; /* Dim the non-active images */
  transform: scale(0.9); /* Slightly reduce the size */
}

/* Styling for the active slide */
.swiper-slide-active .slide-image {
  height: 70vh; /* Increase the height for active slides */
  filter: none; /* Remove blur for the active image */
  opacity: 1; /* Fully visible */
  transform: scale(1); /* Full size */
  border-radius:20px;
}


/* Hide default Swiper navigation buttons */
.swiper-button-next,
.swiper-button-prev {
  display: none; /* Hides default arrows */
}

/* Custom Previous Button */
.custom-prev-button {
  position: absolute;
  left: 20px;
  top: 50%;
  transform: translateY(-50%);
  color: white;
  padding: 10px 20px;
  border-radius: 8px;
  cursor: pointer;
  font-size: 16px;
  font-weight: bold;
  height: 80vh;
    width: 90px;
  z-index: 10;
  user-select: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.custom-prev-button:hover {
  transform: scale(1.05);
}

/* Custom Next Button */
.custom-next-button {
    position: absolute;
    right: 20px;
    top: 10%;
    transform: translateY(-50%);
    color: white;
    border-radius: 8px;
    cursor: pointer;
    font-size: 16px;
    font-weight: bold;
    z-index: 10;
    height: 80vh;
    width: 90px;
    -webkit-user-select: none;
    -moz-user-select: none;
    user-select: none;
    transition: background-color 0.3s ease, transform 0.3s ease;
}

.custom-next-button:hover {
  
  transform: scale(1.05);
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