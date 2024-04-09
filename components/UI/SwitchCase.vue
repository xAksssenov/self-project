<template>
    <div>
        <label
            :class="{ 'switch-checked': value }"
            class="switch relative inline-block w-28 h-14 border-2 border-solid border-white cursor-pointer rounded-full"
        >
            <input v-model="value" class="opacity-0 w-0 h-0" type="checkbox" />
            <span
                class="slider top-px left-px absolute h-12 w-12 rounded-full bg-white border-2 border-black transition-all duration-500"
            />
        </label>
    </div>
</template>

<script setup lang="ts">
const emit = defineEmits(['update:model-value'])

const props = defineProps<{ modelValue: boolean }>()

const value = computed({
    get() {
        return props.modelValue
    },
    set(value: boolean) {
        emit('update:model-value', value)
    },
})
</script>

<style scoped lang="scss">
input:checked + .slider {
    background-color: black;
    transform: translateX(3.2rem);
}

.switch-checked {
    border-color: black;
}
</style>
