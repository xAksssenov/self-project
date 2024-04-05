<template>
    <NuxtCarousel :items-to-show="3.95" :wrap-around="true" :transition="500">
        <NuxtSlide :index="1">
            <NuxtLink href="#">
                <img class="rounded-3xl" src="/assets/img/project-1.jpg" alt="Slide 1" />
            </NuxtLink>
        </NuxtSlide>
        <NuxtSlide :index="2">
            <NuxtLink href="#">
                <img class="rounded-3xl" src="/assets/img/project-2.jpg" alt="Slide 2" />
            </NuxtLink>
        </NuxtSlide>
        <NuxtSlide :index="3">
            <NuxtLink href="#">
                <img class="rounded-3xl" src="/assets/img/project-3.jpg" alt="Slide 3" />
            </NuxtLink>
        </NuxtSlide>
        <NuxtSlide :index="4">
            <NuxtLink href="#">
                <img class="rounded-3xl" src="/assets/img/project-4.jpg" alt="Slide 4" />
            </NuxtLink>
        </NuxtSlide>
        <NuxtSlide :index="5">
            <NuxtLink href="#">
                <img class="rounded-3xl" src="/assets/img/project-5.jpg" alt="Slide 5" />
            </NuxtLink>
        </NuxtSlide>
        <NuxtNavigation />
    </NuxtCarousel>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.carousel__slide {
    padding: 0.5rem;
    opacity: 0.9;
    transform: rotateY(-20deg) scale(0.9);
    border-radius: 3rem;
}

.carousel__viewport {
    perspective: 2000px;
}

.carousel__track {
    transform-style: preserve-3d;
}

.carousel__slide--sliding {
    transition: 0.5s;
}

.carousel__slide--active ~ .carousel__slide {
    transform: scale(0.9);
}

.carousel__slide--prev {
    opacity: 1;
    transform: scale(0.9);
}

.carousel__slide--next {
    opacity: 1;
    transform: rotateY(10deg) scale(0.95);
}

.carousel__slide--active {
    opacity: 1;
    transform: rotateY(0) scale(1.1);
}
</style>
