<template>
    <div class="flex flex-col items-center justify-center px-6 py-12 text-center">
        <div v-if="$slots.icon" class="mb-4 flex size-14 items-center justify-center rounded-2xl border" :class="accent === 'pink' ? 'border-[rgba(255,47,157,0.35)] bg-[rgba(255,47,157,0.1)] text-[var(--ct-pink)]' : 'border-[var(--ct-border)] bg-[rgba(79,168,255,0.08)] text-[var(--ct-blue)]'">
            <slot name="icon"></slot>
        </div>
        <div class="text-base font-semibold text-[var(--ct-text)]">{{ title }}</div>
        <div v-if="description" class="mt-1 max-w-sm text-sm text-[var(--ct-dim)]">{{ description }}</div>
        <div v-if="$slots.action" class="mt-5">
            <slot name="action"></slot>
        </div>
    </div>
</template>

<script>
export default {
    name: "EmptyState",
    props: {
        title: {
            type: String,
            required: true,
        },
        description: {
            type: String,
            default: null,
        },
        accent: {
            type: String,
            default: "blue",
        },
    },
};
</script>
