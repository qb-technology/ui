<script setup lang='ts'>
interface pr {
  title?: string,
  description?: string,
  step?: number | string
}

const props = withDefaults(defineProps<pr>(), {
  title: 'Fast',
  description: 'Egestas elit dui scelerisque ut eu purus aliquam vitae habitasse.'
})


</script>

<template>
  <UCard :ui="{ body: { base: 'flex flex-col gap-4 text-center' }, background: '' }">
    <p class="text-base md:text-lg font-semibold capitalize">{{ props.title }}</p>
    <p class="text-sm/4 text-gray-500 dark:text-gray-400 flex-grow block">{{ props.description }}</p>
    <div class="flex flex-col items-center justify-normal">
      <UButton :label="`Step ${step}`" variant="outline" :ui="{ rounded: 'rounded-md' }" />
    </div>
  </UCard>
</template>