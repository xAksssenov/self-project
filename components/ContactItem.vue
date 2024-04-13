<template>
    <div
        v-if="!messageSent"
        id="contact"
        class="contact-animation lg:my-28 my-10 flex flex-col items-center lg:gap-16 gap-8 relative"
    >
        <h2 class="lg:text-7xl text-4xl w-fit">Для быстрой связи со мной</h2>
        <form
            method="POST"
            data-netlify="true"
            action="/server/contact.php"
            class="flex flex-col lg:gap-8 gap-4 items-center xl:w-1/4"
        >
            <input
                v-model="name"
                class="lg:px-10 px-5 lg:py-6 py-3 bg-white lg:text-4xl text-3xl rounded-3xl w-full text-black font-sans"
                name="name"
                type="text"
                required
                placeholder="Введите имя"
            />
            <input
                v-model="email"
                class="lg:px-10 px-5 lg:py-6 py-3 bg-white lg:text-4xl text-3xl rounded-3xl w-full text-black font-sans"
                name="email"
                type="email"
                required
                placeholder="Введите почту"
            />
            <textarea
                id="1"
                v-model="message"
                class="lg:px-10 px-5 lg:py-6 py-3 bg-white lg:text-4xl text-3xl rounded-3xl text-black w-full lg:h-80 h-64 resize-none outline-none border-none font-sans"
                name="area"
                required
                placeholder="Введите текст"
            />
        </form>
        <SvgoIconContact
            class="contact-svg absolute right-96 top-12 2xl:block hidden"
            filled
        />
        <ButtonItem
            class="lg:text-5xl text-3xl lg:py-7 py-3 lg:px-28 px-14"
            type="submit"
            @click="sendMessage"
        >
            Отправить
        </ButtonItem>
        <h3 class="lg:text-5xl text-2xl w-fit opacity-30">Сообщение придет мне на почту</h3>
    </div>
    <h3 v-else class="lg:text-7xl text-4xl text-red-300 mx-auto w-fit">
        Ваше сообщение отправлено
    </h3>
</template>

<script setup lang="ts">
const name = ref('')
const email = ref('')
const message = ref('')
const messageSent = ref(false)

function sendMessage() {
    name.value = ''
    email.value = ''
    message.value = ''
    messageSent.value = true
}
</script>

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
