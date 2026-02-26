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

    transition-duration: 0.2s;
}

.button--green {
    background: #43716B;
    color: white;
}

.button--green:hover {
    background: #355a55;
    box-shadow: 0 4px 20px rgba(67, 113, 107, 0.4);
    transform: translateY(-2px);
}

.button--white {
    background: #FFFFFF;
    color: #000;
    border: 1px solid #355a55;
}

.button--white:hover {
    background: #F0F0F0;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.15);
    transform: translateY(-2px);
}
</style>