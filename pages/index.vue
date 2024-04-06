<template>
    <div class="mx-20" :class="{ loading: loading }">
        <div v-if="!loading" class="my-20 flex relative">
            <SvgoIconBackground class="img ml-auto svg-animation-bg" filled />
            <SvgoIconTitle class="svg-animation-text absolute left-24 bottom-40" filled />
        </div>
        <div class="flex mx-28 justify-between items-center">
            <div class="title-animation flex flex-col items-end w-6/12 relative">
                <h2 class="text-7xl w-fit">Привет, меня зовут Кирилл</h2>
                <p class="my-1 text-3xl w-fit text-red-300">Aksenov Kirill</p>
                <SvgoIconAbout class="me absolute -top-36 -right-72" filled />
                <h3 class="text-5xl text-end mt-8">
                    Я студент 2 курса Московского Политеха. Учусь на направлении
                    веб-разработка, также заканчивал курс Дополнительного профессионального
                    образования по той же специальности. Разработкой занимаюсь не первый год и
                    за это время смог поучавстовать в различных проектах, о которых вы можете
                    прочитать ниже.
                </h3>
            </div>
            <img class="img-animation" src="/assets/img/photo.png" alt="photo" />
        </div>
        <div class="lines-animation">
            <div class="-rotate-3">
                <RunningLine class="running-animation-first" />
            </div>
            <div class="rotate-3">
                <RunningLine class="running-animation-second" />
            </div>
        </div>
        <div class="flex mx-28 justify-between items-center">
            <SkillsItem />
        </div>
        <div class="slider-animation mt-52">
            <SliderCarousel v-if="isLoaded" />
        </div>
        <div class="lines-animation">
            <div class="rotate-3">
                <RunningLine class="running-animation-first" />
            </div>
            <div class="-rotate-3">
                <RunningLine class="running-animation-second" />
            </div>
        </div>
        <div class="lines-animation my-20 flex relative">
            <SvgoIconBackground class="img ml-auto" filled />
            <SvgoIconTitleSecond class="absolute left-24 bottom-40" filled />
        </div>
        <div class="buttons-animation flex flex-col w-6/12 mx-auto">
            <AnswerItem />
        </div>
    </div>
</template>

<script setup lang="ts">
const loading = ref(true)

setTimeout(() => {
    loading.value = false
}, 1000)

const isLoaded = ref(false)

onMounted(() => {
    isLoaded.value = true
})

function scroll() {
    const move = document.querySelectorAll(
        '.title-animation, .img-animation, .lines-animation, .buttons-animation, .slider-animation',
    )

    for (let i = 0; i < move.length; i++) {
        const windowHeight = window.innerHeight
        const elementTop = move[i].getBoundingClientRect().top
        const elementVisible = 150
        if (elementTop < windowHeight - elementVisible) {
            move[i].classList.add('active')
        } else {
            move[i].classList.remove('active')
        }
    }
}

onMounted(() => {
    window.addEventListener('scroll', scroll)
})
</script>

<style lang="scss">
.loading {
    visibility: hidden;
    opacity: 0;
    transition:
        visibility 0s 2s,
        opacity 2s ease;
}

.nuxt-icon {
    width: 100rem;
    height: 50rem;
}

.nuxt-icon.img {
    width: 100rem;
    height: 70rem;
}

.nuxt-icon.me {
    width: 35rem;
    height: 25rem;
}

.title-animation {
    transform: translateX(-220px);
    opacity: 0;
    transition: 2s all ease;
}

.title-animation.active {
    transform: translateX(0);
    opacity: 1;
}

.img-animation {
    transform: translateX(220px);
    opacity: 0;
    transition: 2s all ease;
}

.img-animation.active {
    transform: translateX(0);
    opacity: 1;
}

.lines-animation {
    opacity: 0;
    transition: opacity 2s ease;
}

.lines-animation.active {
    opacity: 1;
}

.buttons-animation {
    transform: scale(0.3);
    opacity: 0;
    transition: 2s all ease;
}

.buttons-animation.active {
    transform: scale(1);
    opacity: 1;
}

.slider-animation {
    transform: translateX(100%);
    opacity: 0;
    transition: 2s all ease;
}

.slider-animation.active {
    transform: translateX(0%);
    opacity: 1;
}

@keyframes fade-bg {
    0% {
        opacity: 0;
        transform: translateY(30px);
    }

    100% {
        opacity: 1;
        transform: translateY(0);
    }
}

.svg-animation-bg {
    animation: fade-bg 1.5s ease;
}

@keyframes fade-text {
    0% {
        opacity: 0;
        transform: translateX(-200px);
    }

    30% {
        opacity: 0;
    }

    100% {
        opacity: 1;
        transform: translateX(0);
    }
}

.svg-animation-text {
    animation: fade-text 2.5s ease;
}

@keyframes run-one {
    0% {
        transform: translateX(24.35%);
    }

    100% {
        transform: translateX(-20%);
    }
}

.running-animation-first {
    animation: run-one 4s linear infinite;
}

@keyframes run-two {
    0% {
        transform: translateX(-24.35%);
    }

    100% {
        transform: translateX(20%);
    }
}

.running-animation-second {
    animation: run-two 4s linear infinite;
}
</style>