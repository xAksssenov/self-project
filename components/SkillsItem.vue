<template>
    <div class="buttons-animation flex flex-col items-center lg:w-6/12 relative">
        <h3 class="lg:text-5xl text-3xl mb-8 text-4xl lg:text-end text-center">
            Список навыков/умений:
        </h3>
        <SvgoIconSkills class="me absolute lg:top-8 top-4 lg:-right-72 -right-32" filled />
        <div class="grid gap-8 grid-cols-2 justify-items-center">
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                HTML/CSS
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                JS/TS
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                SCSS/SASS
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                GIT
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                TAILWIND
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                VUE
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                NUXT
            </ButtonItem>
            <ButtonItem class="lg:text-5xl lg:py-7 lg:px-28 text-2xl py-4 px-12">
                FIGMA/TILDA
            </ButtonItem>
        </div>
    </div>
    <CubeItem />
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped></style>
