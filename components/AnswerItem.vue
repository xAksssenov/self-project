<template>
    <h2 class="text-7xl mt-8">Часто задаваемые вопросы</h2>
    <ul>
        <li v-for="(question, index) in questions" :key="index">
            <div
                class="flex flex-row justify-between items-end relative after:h-px after:bg-gray-500 after:w-full after:absolute after:top-28"
            >
                <h3 class="text-5xl mt-12">{{ question.question }}</h3>
                <button
                    :style="{ transform: question.open ? 'rotate(45deg)' : '' }"
                    @click="toggleAnswer(index)"
                >
                    <SvgoIconPlus class="plus" filled />
                </button>
            </div>
            <p
                v-if="question.open"
                class="text-4xl mt-12 text-gray-400"
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
