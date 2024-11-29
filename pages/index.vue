<script setup>

</script>

<template>
    <div class="container mx-auto flex justify-center flex-wrap gap-2">
        <!-- <div class="wrapper-btn-1">
            <span> </span>
            <span> </span>
            <span> </span>
            <span> </span> -->
        <!-- <NuxtLink to="/bina-medika-dhc" class="btn-custom">
            Bina Medika Dhc
        </NuxtLink> -->
        <!-- </div> -->
        <UiButton to="/bina-medika-dhc">
            Bina Medika Dhc
        </UiButton>
        <UiButton to="/patrajasa">
            Patrajasa
        </UiButton>
        <UiButton to="/pedeve">
            Pedeve
        </UiButton>
        <UiButton to="/pelita-air">
            Pelita Air
        </UiButton>
        <UiButton to="/ptc">
            PTC
        </UiButton>
        <UiButton to="/sh-cnt">
            SH c&t
        </UiButton>
        <UiButton to="/sh-gas">
            SH gas
        </UiButton>
        <UiButton to="/sh-gas">
            SH gas
        </UiButton>
        <UiButton to="/sh-iml">
            SH iml
        </UiButton>
        <UiButton to="/sh-pnre">
            SH pnre
        </UiButton>
        <UiButton to="/sh-r&p">
            SH r&p
        </UiButton>
        <UiButton to="/sh-upstream">
            sh upstream
        </UiButton>
        <UiButton to="/tugu-insurance">
            tugu insurance
        </UiButton>
    </div>
</template>


<style scoped>
.btn-custom{
    color: #FFF;
    padding: 10px 20px;
    border-radius: 10.295px;
    border: 1.287px solid #FFF;
    background: radial-gradient(100% 100% at 50% 0%, rgba(255, 255, 255, 0.30) 0%, rgba(255, 255, 255, 0.00) 100%), linear-gradient(94deg, #66B7C0 1.69%, #66B7C0 10.23%, #8AC6EC 54%, #66B7C0 91.36%, #66B7C0 99.83%);
}

.wrapper-btn-1 span:nth-child(1) {
	position: absolute;
	top: 0;
	right: 0;
	width: 100%;
	height: 3px;
	background: linear-gradient(to right, #171618, #fff);
	animation: animate1 2s linear infinite;
}

@keyframes animate1 {
	0% {
		transform: translateX(-100%);
	}
	100% {
		transform: translateX(100%);
	}
}

.wrapper-btn-1 span:nth-child(2) {
	position: absolute;
	top: 0;
	right: 0;
	height: 100%;
	width: 3px;
	background: linear-gradient(to bottom, #171618, #fff);
	animation: animate2 2s linear infinite;
	animation-delay: 1s;
}
@keyframes animate2 {
	0% {
		transform: translateY(-100%);
	}
	100% {
		transform: translateY(100%);
	}
}

.wrapper-btn-1 span:nth-child(3) {
	position: absolute;
	bottom: 0;
	right: 0;
	width: 100%;
	height: 3px;
	background: linear-gradient(to left, #171618, #fff);
	animation: animate3 2s linear infinite;
}

@keyframes animate3 {
	0% {
		transform: translateX(100%);
	}
	100% {
		transform: translateX(-100%);
	}
}

.wrapper-btn-1 span:nth-child(4) {
	position: absolute;
	top: 0;
	left: 0;
	height: 100%;
	width: 3px;
	background: linear-gradient(to top, #171618, #fff);
	animation: animate4 2s linear infinite;
	animation-delay: 1s;
}

@keyframes animate4 {
	0% {
		transform: translateY(100%);
	}
	100% {
		transform: translateY(-100%);
	}
}

.wrapper-btn-1{
    padding: 15px;
    border-radius: 10.295px;
    position: relative;
    overflow: hidden;

}
</style>