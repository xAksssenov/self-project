<template>
    <section>
        <NuxtCarousel :items-to-show="itemsToShow" :wrap-around="true" :transition="500">
            <NuxtSlide v-for="slide in slides" :key="slide.index" :index="slide.index">
                <img class="rounded-3xl" :src="slide.image" :alt="'Slide ' + slide.index" />
                <button
                    class="lg:mx-4 mx-2 lg:text-2xl text-xl lg:py-3 py-1 lg:px-10 px-4 rounded-full border-2 border-solid border-red-300 cursor-pointer transition-transform duration-500 ease transform hover:scale-110"
                    @click="showDrop(slide.index)"
                >
                    Подробнее
                </button>
            </NuxtSlide>
        </NuxtCarousel>
        <transition name="scale">
            <DropInformation
                v-if="dropIndex !== null"
                :show="dropVisible"
                :image="slides[dropIndex]?.image"
                :drop-text="slides[dropIndex]?.text"
                :drop-link="slides[dropIndex]?.link"
                @update:show="closeDrop"
                @click.self="closeDrop"
            />
        </transition>
    </section>
</template>

<script setup lang="ts">
const dropIndex = ref()
const dropVisible = ref(false)

function showDrop(index: number) {
    dropVisible.value = !dropVisible.value
    dropIndex.value = index - 1

    if (dropVisible.value) {
        window.addEventListener('scroll', closeDrop, true)
    }
}

function closeDrop() {
    dropVisible.value = false
    dropIndex.value = null
    window.removeEventListener('scroll', closeDrop, true)
}

const slides = [
    {
        index: 1,
        image: '/project-1.jpg',
        text: 'Данный проект сейчас находится в разработке, поэтому ссылку на него я оставить не могу, но работа идет полным ходом. Также данная платформа есть на платформе Figma, в разработке которой я принимал участие, но ссылку по понятным причинам оставить не могу. Ожидайте в скором времени.',
        link: 'https://gitlab.com/knoli/frontend/web',
    },
    {
        index: 2,
        image: '/project-2.jpg',
        text: 'Данный макет был разработам в рамках дисциплины Проектирование пользовательских интерфейсов. Проект Figma в работу не пускался, поэтому присутвует только в виде макета.',
        link: 'https://www.figma.com/file/py2Z9nqDque911QAjhgmAY/%D0%9F%D0%BE%D0%B8%D1%81%D0%BA-%D0%B4%D0%BE%D0%BC%D0%B0%D1%88%D0%BD%D0%B8%D1%85-%D0%B6%D0%B8%D0%B2%D0%BE%D1%82%D0%BD%D1%8B%D1%85?type=design&node-id=0%3A1&mode=design&t=Q5TOAlwTQfTX11Dh-1',
    },
    {
        index: 3,
        image: '/project-3.jpg',
        text: 'Данный проект был создан первым при знакомстве с Vue.js. Он включает в себя Api запросы с созданием комметраев и публикации их. Вы можете опробовать данный проект по ссылке. ',
        link: 'http://aksenov-vue.std-2581.ist.mospolytech.ru',
    },
    {
        index: 4,
        image: '/project-4.jpg',
        text: 'Данный проект был разработан при изучении HTML/CSS, поэтому помимо верстки ничего в себе не подразумевает. Сайт написан без использования чего-либо, просто верстка.',
        link: 'https://beautifulmary.netlify.app',
    },
    {
        index: 5,
        image: '/project-5.jpg',
        text: 'Данный проект был разработан для применения моих навыков на практике. Сайт написан при использовании Nuxt.js. Здесь я попытался максимально проявить свои навыки в плане дизайна и создания веб-приложений.',
        link: 'https://aksenov.netlify.app',
    },
]

const itemsToShow = ref(3.95)

const updateItemsToShow = () => {
    itemsToShow.value = window.innerWidth < 1280 ? 2.95 : 3.95
    itemsToShow.value = window.innerWidth < 768 ? 1.5 : 3.95
}

onMounted(() => {
    updateItemsToShow()
    window.addEventListener('resize', updateItemsToShow)
})

onBeforeUnmount(() => {
    window.removeEventListener('resize', updateItemsToShow)
})
</script>

<style lang="scss" scoped>
.carousel__slide {
    padding: 3rem 0.5rem;
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

.scale-enter-active,
.scale-leave-active {
    transition: all 0.5s ease;
}

.scale-enter-from,
.scale-leave-to {
    opacity: 0;
    transform: scale(0);
}
</style>
