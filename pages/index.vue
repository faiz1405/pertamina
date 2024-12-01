<script setup>

</script>

<template>
    <div
        class="container absolute flex flex-wrap justify-center h-auto gap-2 mx-auto transform -translate-x-1/2 -translate-y-1/2 top-1/2 left-1/2 w-100">
        <div class="grid grid-cols-3 gap-8">
            <!-- Button -->
            <div class="flex items-center justify-center col-span-3">
                <UiButton to="/sh-gas" type="blue">
                    SH GAS
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/sh-upstream" type="blue">
                    SH UPSTREAM
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/sh-iml" type="blue">
                    SH IML
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/pedeve" type="gold">
                    PEDEVE
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/sh-pnre" type="blue">
                    SH PNRE
                </UiButton>
            </div>
            <div class="flex items-center justify-center row-span-2">
                <UiButton to="#" type="gray">
                    HOLDING
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/ptc" type="gold">
                    PTC
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/sh-cnt" type="blue">
                    SH C&T
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/pelita-air" type="gold">
                    PELITA AIR
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/sh-r&p" type="blue">
                    SH R&P
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/patrajasa" type="gold">
                    PATRAJASA
                </UiButton>
            </div>
            <div class="flex items-center justify-center">
                <UiButton to="/tugu-insurance" type="gold">
                    TUGU INSURANCE
                </UiButton>
            </div>
            <div class="flex items-center justify-center col-span-3">
                <UiButton to="/bina-medika-ihc" type="gold">
                    BINA MEDIKA IHC
                </UiButton>
            </div>
        </div>


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