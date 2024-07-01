<script setup lang='ts'>
interface pr {
  icon?: string,
  title?: string,
  description?: string
}

const props = withDefaults(defineProps<pr>(), {
  icon: 'heroicons:rocket-launch',
  title: 'Fast',
  description: 'Egestas elit dui scelerisque ut eu purus aliquam vitae habitasse.'
})


</script>

<template>
  <UCard :ui="{ body: { base: 'flex flex-col gap-4' } }">
    <UIcon :name="props.icon" class="w-12 h-12" :ui="{ rounded: 'rounded-md' }" />
    <p class="font-base font-bold capitalize">{{ props.title }}</p>
    <p class="text-sm/4 text-gray-500 dark:text-gray-400">{{ props.description }}</p>
  </UCard>
</template>