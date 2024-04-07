<template>
    <div class="buttons-animation flex flex-col items-center w-6/12 relative">
        <h3 class="text-5xl mb-8 text-4xl text-end">Список навыков/умений:</h3>
        <SvgoIconSkills class="me absolute top-8 -right-72" filled />
        <div class="grid gap-8 grid-cols-2 justify-items-center">
            <ButtonItem class="text-5xl py-7 px-28">HTML</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">JS/TS</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">CSS/SCSS/SASS</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">GIT</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">TAILWIND</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">VUE</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">NUXT</ButtonItem>
            <ButtonItem class="text-5xl py-7 px-28">FIGMA/TILDA</ButtonItem>
        </div>
    </div>
    <CubeItem />
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped></style>
