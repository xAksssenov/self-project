<template>
    <NuxtLink
        href="/contact"
        class="link py-10 px-24 text-5xl m-4 rounded-3xl border-2 border-solid border-red-300 cursor-pointer"
    >
        Contact me
        <SvgoIconBell class="bell" filled />
    </NuxtLink>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.nuxt-icon.bell {
    position: absolute;
    top: 0.5rem;
    right: 0.5rem;
    width: 2rem;
    height: 2rem;
}

@keyframes bell {
    7% {
        transform: rotateZ(0);
        scale: (1);
    }

    15% {
        transform: rotateZ(-15deg);
    }

    20% {
        transform: rotateZ(10deg);
    }

    25% {
        transform: rotateZ(-10deg);
    }

    30% {
        transform: rotateZ(6deg);
    }

    35% {
        transform: rotateZ(-4deg);
    }

    40% {
        transform: rotateZ(0);
        scale: (1.2);
    }
}

.link {
    animation: bell 2s linear infinite;
}
</style>
