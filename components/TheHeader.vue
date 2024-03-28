<template>
    <header class="sticky top-0 bg-zinc-900/70 backdrop-blur z-50 header-animation">
        <div
            class="flex justify-between items-center mx-20 py-8 relative after:h-px after:bg-white after:w-full after:absolute after:bottom-0"
        >
            <div class="flex gap-20">
                <NuxtLink class="text-4xl text-red-300" href="#">Aksenov Kirill</NuxtLink>
                <NuxtLink class="text-4xl" href="#">
                    Frontend Developer/Designer UI/UX
                </NuxtLink>
            </div>
            <div class="flex gap-10">
                <NuxtLink class="text-4xl" href="#">About</NuxtLink>
                <NuxtLink class="text-4xl" href="#">Works</NuxtLink>
                <NuxtLink class="text-4xl" href="#">Contact</NuxtLink>
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
    animation: fade-in 2s ease;
}
</style>
