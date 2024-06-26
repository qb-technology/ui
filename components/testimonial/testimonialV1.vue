<script setup lang='ts'>
import type { Avatar } from "#ui/types"
type testimonyProp = {
    name: string,
    position?: string,
    msg: string,
    avatar: Avatar,
    url?: string
}

const props = withDefaults(defineProps<testimonyProp>(), {
    name: 'Andrews',
    position: 'Founder of QB Tech',
    msg: 'QB Tech provided for our company the best website that increased our conversion by 20%. Response from our clients on the ui and ux has been wonderful. I highly recommend QB Tech services for any project.',
    avatar: {
        src: 'https://avatars.githubusercontent.com/u/739984?v=4',
        alt: 'Andrews Boateng Okyere'
    } as any,
    url: 'https://github.com/cybandy'
})

</script>

<template>
    <UCard :ui="{ body: { base: 'flex flex-col gap-6' } }">
        <q class="text-gray-600 dark:text-gray-300">{{ props.msg }}</q>
        <div class="flex items-center gap-3 relative">
            <UAvatar v-bind="props.avatar" :alt="props.avatar.alt ?? props.name" size="sm" />
            <div>
                <ULink :to="url" target="_blank" rel="noopener noreferrer" :arial-label="props.name"
                    class="focus:outline-none" tabindex="-1">
                    <p class="font-semibold text-sm">{{ props.name }}</p>
                    <p class="text-gray-500 dark:text-gray-400 text-sm">{{ position }}</p>
                </ULink>
            </div>
        </div>
    </UCard>
</template>