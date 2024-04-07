<template>
    <div
        id="contact"
        class="contact-animation my-28 flex flex-col items-center gap-16 relative"
    >
        <h2 class="text-7xl w-fit">Для быстрой связи со мной</h2>
        <div class="flex flex-col gap-8 items-center w-1/4">
            <input
                class="px-10 py-6 bg-white text-4xl rounded-3xl w-full text-black font-sans"
                type="text"
                placeholder="Введите имя"
            />
            <input
                class="px-10 py-6 bg-white text-4xl rounded-3xl w-full text-black font-sans"
                type="mail"
                placeholder="Введите почту"
            />
            <textarea
                id="1"
                class="px-10 py-6 bg-white text-4xl rounded-3xl text-black w-full h-80 resize-none outline-none border-none font-sans"
                name="area"
                placeholder="Введите текст"
            />
        </div>
        <SvgoIconContact class="contact-svg absolute right-96 top-12" filled />
        <ButtonItem class="text-5xl py-7 px-28">Отправить</ButtonItem>
        <h3 class="text-5xl w-fit opacity-30">Сообщение придет мне на почту</h3>
    </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.nuxt-icon.contact-svg {
    width: 30rem;
    height: 30rem;
}
</style>
