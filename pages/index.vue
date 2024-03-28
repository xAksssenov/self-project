<template>
    <div class="mx-20" :class="{ loading: loading }">
        <div v-if="!loading" class="my-20 flex relative">
            <SvgoIconBackground class="img ml-auto svg-animation-bg" filled />
            <SvgoIconTitle class="absolute left-24 bottom-40 svg-animation-text" filled />
        </div>
    </div>
</template>

<script setup lang="ts">
const loading = ref(true)

setTimeout(() => {
    loading.value = false
}, 1000)
</script>

<style lang="scss" scoped>
.nuxt-icon {
    width: 100rem;
    height: 50rem;
}

.nuxt-icon.img {
    width: 100rem;
    height: 70rem;
    align-self: flex-end;
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
    animation: fade-bg 2s ease;
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
    animation: fade-text 3s ease;
}

.loading {
    visibility: hidden;
    opacity: 0;
    transition:
        visibility 0s 2s,
        opacity 2s ease;
}
</style>
