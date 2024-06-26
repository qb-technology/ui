<script setup lang='ts'>

defineProps({
    faviconClass: {
        type: String,
        default: 'text-primary w-[59px] h-[53px]'
    },
    textClass: {
        type: String,
        default: 'text-lg sm:text-2xl uppercase'
    }
})
</script>

<template>
    <div class="flex items-center gap-1">
        <LogoFavicon :class="faviconClass" />
        <span :class="textClass" class="leading-tight font-bold">qb tech</span>
    </div>
</template>