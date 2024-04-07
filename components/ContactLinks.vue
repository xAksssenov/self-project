<template>
    <div class="flex mx-20 justify-between items-start">
        <div class="links-animation">
            <div id="about" class="my-28 flex flex-col items-start w-2/3 relative">
                <h2 class="text-7xl w-fit">
                    Если вам понравился данный сайт, то дайте пожалуйста отзыв
                </h2>
                <p class="my-2 text-3xl w-fit text-red-300">Aksenov Kirill</p>
                <SvgoIconAboutAgain class="me absolute top-16 -left-3" filled />
            </div>
            <div class="flex flex-row gap-12 items-start">
                <NuxtLink
                    class="transition-transform duration-500 ease transform hover:-translate-y-3"
                    href="https://github.com/xAksssenov"
                    target="_blank"
                >
                    <SvgoIconGit class="links" filled />
                </NuxtLink>
                <NuxtLink
                    class="transition-transform duration-500 ease transform hover:-translate-y-3"
                    href="https://vk.com/iallcab"
                    target="_blank"
                >
                    <SvgoIconVk class="links" filled />
                </NuxtLink>
                <NuxtLink
                    class="transition-transform duration-500 ease transform hover:-translate-y-3"
                    href="https://t.me/iallcab"
                    target="_blank"
                >
                    <SvgoIconTg class="links" filled />
                </NuxtLink>
                <NuxtLink
                    class="transition-transform duration-500 ease transform hover:-translate-y-3"
                    href="mailto:aks.kirill32@gmail.com"
                >
                    <SvgoIconEmail class="links" filled />
                </NuxtLink>
            </div>
        </div>
        <CubeItem class="my-40 mx-48" />
    </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.nuxt-icon.links {
    width: 5rem;
    height: 5rem;
}
</style>
