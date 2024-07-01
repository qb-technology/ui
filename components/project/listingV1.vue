<script lang="ts" setup>
defineProps({
    image: String,
    favicon: String,
    title: {
        type: String,
        default: 'Kids Academy'
    },
    desc: {
        type: String,
        default: 'UI/UX Design & Development'
    },
    to: {
        type: String,
        default: '#'
    },
    isActive: Boolean,
    color: {
        type: String,
        default: 'primary'
    }
})
</script>

<template>
    <div class="p-4 flex flex-col gap-2 w-full h-full">
        <!--image-->
        <NuxtLink :to="to">
            <slot name="image">
                <LazyNuxtImg :src="image" placeholder="/image-placeholoder-dark.png" preset="proImage" width="352"
                    height="238" format="webp" class="w-full aspect-project" />
            </slot>
        </NuxtLink>
        <!--name & icon w/ desc-->
        <div class="flex items-center gap-2.5 max-w-full">
            <slot name="iconTitle">
                <slot name="favicon">
                    <LazyNuxtImg :src="favicon" preset="proFavicon" width="35" height="35" format="webp" />
                </slot>
                <slot name="title">
                    <div class="space-y-2">
                        <p class="font-medium text-pretty">{{ title }}</p>
                        <p class=" text-gray-500 dark:text-gray-400 text-pretty w-full">{{ desc }}</p>
                    </div>
                </slot>
            </slot>
        </div>
        <!--button-->
        <div class="w-full">
            <slot name="button">
                <UButton :to="to" target="_blank" label="View Project" icon="i-heroicons-arrow-top-right-on-square"
                    :variant="isActive ? 'solid' : 'outline'" :color="color" block :ui="{ rounded: 'rounded-md' }" />

            </slot>
        </div>
    </div>
</template>

<style scoped></style>