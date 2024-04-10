<template>
    <h2 class="lg:text-7xl text-4xl lg:mt-8 mt-4">Часто задаваемые вопросы</h2>
    <ul>
        <li v-for="(question, index) in questions" :key="index">
            <div
                class="flex flex-row justify-between items-end relative after:h-px after:bg-gray-500 after:w-full after:absolute lg:after:top-28 after:top-20"
            >
                <h3 class="lg:text-5xl text-3xl lg:mt-12 mt-7">{{ question.question }}</h3>
                <button
                    :style="{ transform: question.open ? 'rotate(45deg)' : '' }"
                    @click="toggleAnswer(index)"
                >
                    <SvgoIconPlus class="plus" filled />
                </button>
            </div>
            <p
                v-if="question.open"
                class="lg:text-4xl text-2xl lg:mt-12 mt-6 text-gray-400"
                :class="{ 'text-answer': question.open }"
            >
                {{ question.answer }}
            </p>
        </li>
    </ul>
</template>

<script setup lang="ts">
const questions = ref([
    {
        question: 'Есть ли у меня коммерческий опыт?',
        answer: 'Такого опыта у меня нет, но я активно участвую в проектах, которые в скором будущем вполне могут стать коммерческими.',
        open: false,
    },
    {
        question: 'Умею ли я работать в команде?',
        answer: 'Конечно да! Я отлично могу коммуницировать с людьми, тем более я быстро обучаюсь и выполняю поставленные задачи.',
        open: false,
    },
    {
        question: 'Согласен ли я у вас работать?',
        answer: 'Опять же да! (конечно же, если мы с вами найдем общий язык, а мы его найдем).',
        open: false,
    },
])

function toggleAnswer(index: number) {
    questions.value[index].open = !questions.value[index].open
}
</script>

<style lang="scss" scoped>
.nuxt-icon.plus {
    width: 3rem;
    height: 3rem;
}

@media (max-width: 1024px) {
    .nuxt-icon.plus {
        width: 1.5rem;
        height: 1.5rem;
    }
}

.text-answer {
    opacity: 0;
    animation: answer 1s ease forwards;
}

@keyframes answer {
    from {
        opacity: 0;
    }

    to {
        opacity: 1;
    }
}
</style>
