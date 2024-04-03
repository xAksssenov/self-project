<template>
    <div class="mx-20" :class="{ loading: loading }">
        <div v-if="!loading" class="my-20 flex relative">
            <SvgoIconBackground class="img ml-auto svg-animation-bg" filled />
            <SvgoIconTitle class="absolute left-24 bottom-40 svg-animation-text" filled />
        </div>
        <div class="flex mx-28 justify-between items-center">
            <div class="title-animation flex flex-col items-end w-6/12 relative">
                <h1 class="text-7xl w-fit">Привет, меня зовут Кирилл</h1>
                <p class="my-1 text-3xl w-fit text-red-300">Aksenov Kirill</p>
                <SvgoAboutMe class="me absolute -top-36 -right-72" filled />
                <h3 class="text-5xl text-end mt-8 text-4xl">
                    Я студент 2 курса Московского Политеха. Учусь на направлении
                    веб-разработка, также заканчивал курс Дополнительного профессионального
                    образования по той же специальности. Разработкой занимаюсь не первый год и
                    за это время смог поучавстовать в различных проектах, о которых вы можете
                    прочитать ниже.
                </h3>
            </div>
            <img class="img-animation" src="/assets/img/photo.png" alt="photo" />
        </div>
    </div>
</template>

<script setup lang="ts">
const loading = ref(true)

setTimeout(() => {
    loading.value = false
}, 1000)

function scrollFirst() {
    const move = document.querySelectorAll('.title-animation, .img-animation')
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
    window.addEventListener('scroll', scrollFirst)
})
</script>

<style lang="scss" scoped>
.title-animation {
    transform: translateX(-220px);
    opacity: 0;
    transition: 2.5s all ease;
}

.title-animation.active {
    transform: translateX(0);
    opacity: 1;
}

.img-animation {
    transform: translateX(220px);
    opacity: 0;
    transition: 2.5s all ease;
}

.img-animation.active {
    transform: translateX(0);
    opacity: 1;
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

.loading {
    visibility: hidden;
    opacity: 0;
    transition:
        visibility 0s 2s,
        opacity 2s ease;
}
</style>
