<template>
    <NuxtCarousel :items-to-show="3.95" :wrap-around="true" :transition="500">
        <NuxtSlide v-for="slide in slides" :key="slide.index" :index="slide.index">
            <img class="rounded-3xl" :src="slide.image" :alt="'Slide ' + slide.index" />
            <ButtonItem class="text-2xl py-3 px-10">Подробнее</ButtonItem>
        </NuxtSlide>
    </NuxtCarousel>
</template>

<script setup lang="ts">
const slides = [
    { index: 1, image: '/project-1.jpg' },
    { index: 2, image: '/project-2.jpg' },
    { index: 3, image: '/project-3.jpg' },
    { index: 4, image: '/project-4.jpg' },
    { index: 5, image: '/project-5.jpg' },
]
</script>

<style lang="scss" scoped>
.carousel__slide {
    padding: 0.5rem;
    opacity: 0.9;
    transform: rotateY(-20deg) scale(0.9);
    border-radius: 3rem;
    display: flex;
    flex-direction: column;
    align-items: center;
    cursor: pointer;
    gap: 1rem;
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
