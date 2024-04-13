<template>
    <div
        id="contact"
        class="contact-animation lg:my-28 my-10 flex flex-col items-center lg:gap-16 gap-8 relative"
    >
        <h2 class="lg:text-7xl text-4xl w-fit">Для быстрой связи со мной</h2>
        <form name="contact" method="POST" data-netlify="true">
            <p>
                <label>Ваше имя: <input type="text" name="name" /></label>
            </p>
            <p>
                <label>Ваша почта: <input type="email" name="email" /></label>
            </p>
            <p>
                <label>Сообщение: <textarea name="message"></textarea></label>
            </p>
            <p>
                <button type="submit">Send</button>
            </p>
        </form>
        <SvgoIconContact
            class="contact-svg absolute right-96 top-12 2xl:block hidden"
            filled
        />
    </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
@use '@/assets/scss/variables' as *;

.nuxt-icon.contact-svg {
    width: 30rem;
    height: 30rem;
}

.light {
    input,
    textarea {
        background-color: $dark-color;
        color: $light-color;
    }
}

.dark {
    input,
    textarea {
        background-color: $light-color;
        color: $dark-color;
    }
}

input:invalid,
textarea:invalid {
    border: 2px solid #fca5a5;
}
</style>
