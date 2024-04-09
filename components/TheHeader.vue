<template>
    <header class="sticky top-0 bg-zinc-900/70 backdrop-blur z-50 header-animation">
        <div
            class="flex justify-between items-center mx-20 py-8 relative after:h-px after:bg-white after:w-full after:absolute after:bottom-0"
        >
            <div class="flex gap-20">
                <NuxtLink
                    class="text-4xl text-red-300 transition-transform duration-500 ease transform hover:-translate-y-2"
                    href="/"
                >
                    Aksenov Kirill
                </NuxtLink>
                <NuxtLink
                    class="text-4xl transition-transform duration-500 ease transform hover:-translate-y-2"
                    href="/"
                >
                    Frontend Developer/Designer UI/UX
                </NuxtLink>
            </div>
            <div class="flex gap-10">
                <button
                    class="text-4xl cursor-pointer transition-transform duration-500 ease transform hover:-translate-y-2"
                    @click="handleAboutClick"
                >
                    About
                </button>
                <button
                    v-if="$route.path !== '/contact'"
                    class="text-4xl cursor-pointer transition-transform duration-500 ease transform hover:-translate-y-2"
                    @click="handleProjectsClick"
                >
                    Projects
                </button>
                <button
                    class="text-4xl cursor-pointer transition-transform duration-500 ease transform hover:-translate-y-2"
                    @click="handleContactClick"
                >
                    Contact
                </button>
            </div>
            <SwitchCase :model-value="switchValue" @update:model-value="handleSwitchChange" />
        </div>
    </header>
</template>

<script setup lang="ts">
const switchValue = ref(false)

function handleSwitchChange() {
    switchValue.value = !switchValue.value
}

watch(switchValue, (newValue) => {
    if (newValue) {
        document.documentElement.classList.add('lightTheme')
        document.documentElement.classList.remove('darkTheme')
    } else {
        document.documentElement.classList.add('darkTheme')
        document.documentElement.classList.remove('lightTheme')
    }
})

function scrollToElement(elementId: string) {
    const element = document.getElementById(elementId)
    if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'center' })
    }
}

function scrollToElementProject(elementId: string) {
    const element = document.getElementById(elementId)
    if (element) {
        element.scrollIntoView({ behavior: 'smooth', block: 'end' })
    }
}

function handleAboutClick() {
    scrollToElement('about')
}

function handleProjectsClick() {
    scrollToElementProject('projects')
}

function handleContactClick() {
    scrollToElement('contact')
}
</script>

<style lang="scss" scoped>
@keyframes fade-in {
    0% {
        transform: translateY(-100px);
    }

    100% {
        transform: translateY(0);
    }
}

.header-animation {
    animation: fade-in 1.5s ease;
    transition: all 0.5s ease;
}
</style>
