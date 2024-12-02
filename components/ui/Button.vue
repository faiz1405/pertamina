<template>
    <NuxtLink :to="link"
        class="relative flex justify-center items-center text-white font-semibold w-[201px] h-[66px] text-center px-6 py-3 transition-all bg-transparent rounded-lg"
        :class="typeButton(type)">
        <slot />

        <NuxtImg v-if="type === 'gray'" :src="Gray"
            class="absolute top-1/2 left-1/2  translate-x-[-50%] translate-y-[-50%] w-full" alt="arrow" title="arrow" />
        <NuxtImg v-if="type === 'gold'" :src="Gold"
            class="absolute top-1/2 left-1/2  translate-x-[-50%] translate-y-[-50%] right-4 w-[110px] h-[70px]"
            alt="arrow" title="arrow" />
        <NuxtImg v-if="type === 'blue'" :src="Blue"
            class="absolute top-1/2 left-1/2  translate-x-[-50%] translate-y-[-50%] right-4 w-[110px] h-[70px]"
            alt="arrow" title="arrow" />

        <div v-if="type === 'blue'"
            class="absolute inset-0 z-[10] flex justify-center items-center opacity-0 hover:opacity-100 transition-opacity duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" width="169" height="169" viewBox="0 0 169 169" fill="none"
                class="animate-svg">
                <!-- SVG content here -->
                <g opacity="0.2" filter="url(#filter0_f_313_3075)">
                    <path
                        d="M79.6887 28.8629L81.1328 69.9254L124.924 20L83.3454 71.7813L148.993 61.6756L83.8469 74.6248L140.634 109.067L82.4028 77.1254L90.2612 105.269L79.6887 78.1129L55.6196 140L76.9746 77.1254L18.7437 109.067L75.5304 74.6248L45.7685 69.9254L76.032 71.7813L34.4536 20L78.2445 69.9254L79.6887 28.8629Z"
                        fill="#96F2FF" />
                </g>
                <g opacity="0.6" filter="url(#filter1_f_313_3075)">
                    <circle cx="84.5096" cy="84.5872" r="32.5243" fill="url(#paint0_radial_313_3075)" />
                </g>
                <circle cx="95.63" cy="126.53" r="1.47" fill="white" class="animate-circle" />
                <circle cx="116.31" cy="121.86" r="1.47" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="85.66" cy="105.41" r="1.47" fill="white" class="animate-circle" />
                <circle cx="94.99" cy="80.31" r="1.47" fill="white" class="animate-circle" />
                <circle cx="78.32" cy="78.14" r="0.59" fill="white" class="animate-circle" />
                <circle cx="66.59" cy="64.06" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="95.33" cy="58.19" r="0.59" fill="white" class="animate-circle" />
                <circle cx="73.05" cy="98.66" r="0.59" fill="white" class="animate-circle" />
                <circle cx="77.15" cy="117.43" r="0.59" fill="white" class="animate-circle" />
                <circle cx="81.26" cy="136.2" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="106.48" cy="110.39" r="0.59" fill="white" class="animate-circle" />
                <circle cx="54.28" cy="106.88" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="55.45" cy="57.02" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="108.24" cy="69.34" r="0.59" fill="white" class="animate-circle" />
                <circle cx="43.13" cy="38.25" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="37.27" cy="103.36" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="68.35" cy="126.82" r="0.59" fill="white" class="animate-circle" />
                <circle cx="131.7" cy="84.59" r="0.59" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="66.3" cy="91.33" r="1.47" fill="white" class="animate-circle" />
                <circle cx="107.36" cy="47.34" r="1.47" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="66.3" cy="33.85" r="1.47" fill="white" class="animate-circle" />
                <circle cx="119.09" cy="81.95" r="1.47" fill="white" class="animate-circle" />
                <circle cx="44.01" cy="83.71" r="1.47" fill="white" class="animate-circle" />
                <defs>
                    <filter id="filter0_f_313_3075" x="10.6298" y="11.8861" width="146.477" height="136.228"
                        filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                        <feFlood flood-opacity="0" result="BackgroundImageFix" />
                        <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
                        <feGaussianBlur stdDeviation="4.05694" result="effect1_foregroundBlur_313_3075" />
                    </filter>
                    <filter id="filter1_f_313_3075" x="0.60247" y="0.680056" width="167.814" height="167.814"
                        filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                        <feFlood flood-opacity="0" result="BackgroundImageFix" />
                        <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
                        <feGaussianBlur stdDeviation="25.6914" result="effect1_foregroundBlur_313_3075" />
                    </filter>
                    <radialGradient id="paint0_radial_313_3075" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse"
                        gradientTransform="translate(84.5096 84.5872) rotate(90) scale(32.5243)">
                        <stop offset="0.685" stop-color="#3FD1FF" />
                        <stop offset="1" stop-color="#266799" />
                    </radialGradient>
                </defs>
            </svg>
        </div>
        <div v-if="type === 'gold'"
            class="absolute inset-0 z-[10] flex justify-center items-center opacity-0 hover:opacity-100 transition-opacity duration-300">
            <svg xmlns="http://www.w3.org/2000/svg" width="161" height="161" viewBox="0 0 161 161" fill="none">
                <g opacity="0.2" filter="url(#filter0_f_313_3223)">
                    <path
                        d="M75.8978 27.4198L77.2697 66.4291L118.871 19L79.3716 68.1923L141.737 58.5918L79.8481 70.8936L133.796 103.614L78.4762 73.2691L85.9416 100.006L75.8978 74.2073L53.0321 133L73.3194 73.2691L18 103.614L71.9474 70.8936L43.6736 66.4291L72.4239 68.1923L32.9245 19L74.5258 66.4291L75.8978 27.4198Z"
                        fill="#EDB94D" />
                </g>
                <g opacity="0.6" filter="url(#filter1_f_313_3223)">
                    <circle cx="80.4775" cy="80.358" r="30.8981" fill="url(#paint0_radial_313_3223)" />
                </g>
                <circle cx="91.0399" cy="120.199" r="1.39305" fill="white" class="animate-circle" />
                <circle cx="110.691" cy="115.765" r="1.39305" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="81.5671" cy="100.139" r="1.39305" fill="white" class=" animate-circle" />
                <circle cx="90.4389" cy="76.298" r="1.39305" fill="white" class="animate-circle" />
                <circle cx="74.6019" cy="74.229" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="63.4575" cy="60.8551" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="90.7613" cy="55.283" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="69.5869" cy="93.7314" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="73.4875" cy="111.562" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="77.388" cy="129.393" r="0.557221" fill="white" class=" animate-circle" />
                <circle opacity="0.7" cx="101.348" cy="104.876" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="51.7558" cy="101.532" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="52.8702" cy="54.1687" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="103.02" cy="65.8705" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="41.1687" cy="36.3374" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="35.5964" cy="98.1888" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="65.1292" cy="120.478" r="0.557221" fill="white" class="animate-circle" />
                <circle cx="125.309" cy="80.3576" r="0.557221" fill="white" class="animate-circle" />
                <circle opacity="0.7" cx="63.1788" cy="86.7657" r="1.39305" fill="white" class="animate-circle" />
                <circle cx="102.184" cy="44.9744" r="1.39305" fill="white" class="animate-circle" />
                <circle opacity="0.4" cx="63.1788" cy="32.1582" r="1.39305" fill="white" class="animate-circle" />
                <circle cx="113.329" cy="77.8506" r="1.39305" fill="white" class="animate-circle" />
                <circle cx="42.0045" cy="79.5222" r="1.39305" fill="white" class="animate-circle" />
                <defs>
                    <filter id="filter0_f_313_3223" x="10.2918" y="11.2918" width="139.153" height="129.416"
                        filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                        <feFlood flood-opacity="0" result="BackgroundImageFix" />
                        <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
                        <feGaussianBlur stdDeviation="3.85409" result="effect1_foregroundBlur_313_3223" />
                    </filter>
                    <filter id="filter1_f_313_3223" x="0.765732" y="0.646179" width="159.424" height="159.424"
                        filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
                        <feFlood flood-opacity="0" result="BackgroundImageFix" />
                        <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape" />
                        <feGaussianBlur stdDeviation="24.4069" result="effect1_foregroundBlur_313_3223" />
                    </filter>
                    <radialGradient id="paint0_radial_313_3223" cx="0" cy="0" r="1" gradientUnits="userSpaceOnUse"
                        gradientTransform="translate(80.4775 80.358) rotate(90) scale(30.8981)">
                        <stop offset="0.685" stop-color="#CA9D38" />
                        <stop offset="1" stop-color="#FB9703" />
                    </radialGradient>
                </defs>
            </svg>
        </div>

    </NuxtLink>
</template>

<script setup>
import Gold from '/img/gold.svg'
import Blue from '/img/blue.svg'
import Gray from '/img/holding.png'
defineProps({
    text: {
        type: String,
        required: true
    },
    link: {
        type: String,
        required: true
    },
    type: {
        type: String,
        required: false
    }
})

function typeButton(type) {
    if (type === 'blue') {
        return 'btn-blue animate-svg btn-after'
    } else if (type === 'gold') {
        return 'btn-gold animate-svg btn-after'
    } else if (type === 'gray') {
        return 'btn-gray'
    }
}
</script>

<style scoped>
.btn-custom{
    color: #FFF;
    padding: 10px 20px;
    border-radius: 10.295px;
    border: 1.287px solid #FFF;
    background: radial-gradient(100% 100% at 50% 0%, rgba(255, 255, 255, 0.30) 0%, rgba(255, 255, 255, 0.00) 100%), linear-gradient(94deg, #66B7C0 1.69%, #66B7C0 10.23%, #8AC6EC 54%, #66B7C0 91.36%, #66B7C0 99.83%);
}
.btn-gold{
    border-radius: 165.217px;
border: 1.652px solid rgba(247, 228, 169, 0.33);
background: linear-gradient(180deg, rgba(247, 228, 169, 0.50) 0%, rgba(255, 172, 0, 0.50) 100%);
box-shadow: 0px -3.304px 9.913px 0px rgba(255, 255, 255, 0.75) inset, 0px -6.609px 26.435px 0px rgba(84, 164, 231, 0.30) inset;
}
.btn-blue{
    border-radius: 165.217px;
border: 1.652px solid rgba(200, 225, 245, 0.33);
background: linear-gradient(180deg, rgba(164, 207, 244, 0.50) 0%, rgba(77, 161, 233, 0.50) 100%);
box-shadow: 0px -3.304px 9.913px 0px rgba(255, 255, 255, 0.75) inset, 0px -6.609px 26.435px 0px rgba(84, 164, 231, 0.30) inset;

transition: all 0.3s ease-in-out;
}

.btn-gray{
    text-shadow: 0px 6px 8px rgba(86,167,234,1);
}

.btn-gray::before{
    content: "";
    opacity: 0.5;
    filter: blur(2.141706705093384px);
}



.btn-blue:hover{
    border-radius: 165.217px;
border: 1.652px solid rgba(200, 225, 245, 0.33);
background: linear-gradient(180deg, rgba(164, 207, 244, 0.50) 0%, rgba(77, 161, 233, 0.50) 100%);
box-shadow: 0px -3.304px 9.913px 0px rgba(255, 255, 255, 0.75) inset, 0px -6.609px 26.435px 0px rgba(84, 164, 231, 0.30) inset;
}

.btn-after::after {
    content: "";
    position: absolute;
    top: 15px;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 162px;
    height: 24px;
    border-radius: 1652.174px;
background: linear-gradient(180deg, #FFF 0%, #FFF 0.01%, rgba(255, 255, 255, 0.00) 100%);
}

.hover\:animate-pulse:hover {
  animation: pulse 1s infinite;
}

.animate-svg {
  transform: scale(0.9);
  transition: transform 0.3s ease-in-out;
}

.hover\:animate-pulse:hover .animate-svg {
  transform: scale(1);
}

/* Animate circles */
.animate-circle {
  transition: transform 0.3s ease, opacity 0.3s ease;
}

/* Hover animation */
.animate-svg:hover .animate-circle {
  animation: move-circle 1s  ease-in-out;
}

@keyframes pulse {
  0% {
    transform: scale(1);
    opacity: 1;
  }
  50% {
    transform: scale(1.1);
    opacity: 0.8;
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

@keyframes move-circle {
  0% {

    opacity: 0;
  }
  100% {
    
    opacity: 1;
  }
}
</style>