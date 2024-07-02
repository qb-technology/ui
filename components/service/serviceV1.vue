<script setup lang='ts'>
interface pr {
    icon?: string,
    title?: string,
    excerpt?: string,
    background?: string,
    handle?: string,
}

const props = withDefaults(defineProps<pr>(), {
    icon: 'heroicons:rocket-launch',
    title: 'Fast',
    excerpt: 'Egestas elit dui scelerisque ut eu purus aliquam vitae habitasse.',
    handle: '#'
})


</script>

<template>
    <ULink :to="handle">
        <UCard v-bind="$attrs"
            :ui="{ body: { base: 'flex flex-col items-center justify-center gap-4 text-center', padding: 'sm:px-4' }, background: '' }">
            <!-- <UIcon :name="props.icon" class="w-12 h-12" /> -->
            <UButton :icon="props.icon" size="xl" variant="soft" square :aria-label="`${props.title} icon`" />
            <p class="text-base font-bold capitalize">{{ props.title }}</p>
            <p class="text-sm/4 text-gray-700 dark:text-gray-300">{{ props.excerpt }}</p>
        </UCard>
    </ULink>
</template>