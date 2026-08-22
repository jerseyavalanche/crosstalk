<template>
    <RouterLink :to="to" v-slot="{ href, route, navigate, isActive }" custom>
        <a 
            :href="href" 
            @click="handleNavigate($event, navigate)" 
            type="button" 
            :class="[
                isActive
                    ? 'bg-[rgba(255,47,157,0.16)] text-white border-[rgba(255,47,157,0.45)] shadow-[0_0_32px_rgba(255,47,157,0.14)]'
                    : 'text-[var(--ct-blue)] border-transparent hover:text-white hover:bg-[rgba(79,168,255,0.08)] hover:border-[var(--ct-border)]'
            ]"
            class="w-full group flex gap-x-3 rounded-r-full border p-2 mr-2 text-sm leading-6 font-semibold transition focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-600"
        >
            <span class="flex shrink-0 items-center opacity-90 group-hover:opacity-100">
                <slot name="icon"></slot>
            </span>
            <span class="flex w-full items-center">
                <slot name="text"></slot>
            </span>
        </a>
    </RouterLink>
</template>


<script>
export default {
    name: 'SidebarLink',
    props: {
        to: Object,
    },
    methods: {
        handleNavigate(event, navigate) {

            // emit click event for SidebarLink element
            this.$emit('click');

            // handle navigation
            navigate(event);

        },
    },
};
</script>
