<script setup lang="ts">
type ButtonVariant = 'green' | 'white'

const props = withDefaults(defineProps<{
    variant?: ButtonVariant
    class?: string
}>(), {
    variant: 'green'
})
</script>

<template>
    <button :class="[
        'button',
        `button--${variant}`,
        props.class
    ]">
        <slot />
    </button>
</template>

<style scoped>
.button {
    padding: 10px 45px;
    border-radius: 6px;
    font-weight: 700;
    font-size: 14px;
    line-height: 19px;
    border: none;
}

.button--green {
    background: #43716B;
    color: white;
}

.button--white {
    background: #FFFFFF;
    color: #000;
}
</style>