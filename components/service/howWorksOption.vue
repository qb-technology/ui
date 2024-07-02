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
  <UCard :ui="{ body: { base: 'flex flex-col gap-4 h-full' }, background: '', base: 'h-full' }">
    <p class="text-base font-semibold capitalize text-center">{{ props.title }}</p>
    <div class="flex-grow grid place-content-center">
      <p class="text-sm/4 text-gray-700 dark:text-gray-300 text-balance text-center">{{ props.description }}</p>
    </div>
    <div class="flex flex-col items-center justify-normal">
      <UButton :label="`Step ${step}`" variant="outline" :ui="{ rounded: 'rounded-md' }" />
    </div>
  </UCard>
</template>