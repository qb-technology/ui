<script setup lang='ts'>
const isOpen = ref(false)

const close = () => isOpen.value = false
</script>

<template>
    <div>
        <UButton @click="isOpen = true" icon="i-heroicons-bars-3-20-solid" color="white" variant="ghost"
            aria-label="navigation menu" />
        <USlideover v-model="isOpen">
            <UCard
                :ui="{ base: 'flex flex-col', body: { base: 'flex-grow' }, header: { base: 'flex items-center justify-between gap-5' } }">
                <template #header>
                    <div>

                    </div>
                    <div class="flex-grow flex items-center justify-center">
                        <DarkMode />
                    </div>
                    <div>
                        <UButton @click="close" color="gray" icon="i-heroicons-x-mark-20-solid" size="xl"
                            aria-label="close menu" />
                    </div>
                </template>

                <UVerticalNavigation :links="menuLinks">
                    <template #default="{ link }">
                        <span @click="close" class="relative">{{ link.label }}</span>
                    </template>
                </UVerticalNavigation>
            </UCard>
        </USlideover>
    </div>
</template>