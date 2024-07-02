<script setup lang='ts'>

</script>

<template>
    <UCard v-bind="$attrs"
        :ui="{ body: { base: 'flex flex-col items-center justify-center gap-4 text-center', padding: 'sm:px-4' }, background: '', base: 'animate-pulse' }">
        <div class="w-8 h-8 rounded-none bg-gray-100 dark:bg-gray-900/50" />
        <div class=" w-36 h-3 bg-gray-100 dark:bg-gray-900/50"></div>
        <div class="flex flex-col items-center justify-center gap-1">
            <div class=" h-3 w-64 bg-gray-100 dark:bg-gray-900/50"></div>
            <div class=" h-3 w-56 bg-gray-100 dark:bg-gray-900/50"></div>
            <div class=" h-3 w-48 bg-gray-100 dark:bg-gray-900/50"></div>
        </div>
    </UCard>
</template>