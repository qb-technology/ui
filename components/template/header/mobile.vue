<script setup lang='ts'>
const isOpen = ref(false)
</script>

<template>
    <div>
        <UButton @click="isOpen = true" icon="i-heroicons-bars-3-20-solid" color="white" variant="ghost" />
        <USlideover v-model="isOpen">
            <UCard>
                <UVerticalNavigation :links="menuLinks" />
            </UCard>
        </USlideover>
    </div>
</template>