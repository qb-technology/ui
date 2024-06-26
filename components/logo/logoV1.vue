<script setup lang='ts'>

defineProps({
    faviconClass: {
        type: String,
        default: 'text-primary w-[59px] h-[53px]'
    },
    textClass: {
        type: String,
        default: 'text-lg sm:text-2xl uppercase'
    },
    img: {
        type: [String, Boolean],
        default: false
    },
    to: {
        type: String,
        default: '/'
    }
})
</script>

<template>
    <ULink :to="to">
        <slot name="logo">
            <div class="flex items-center gap-1">
                <NuxtImg v-if="typeof img == 'string'" :src="img" :class="faviconClass" />
                <LogoFavicon :class="faviconClass" />
                <span :class="textClass" class="leading-tight font-bold">qb tech</span>
            </div>
        </slot>
    </ULink>
</template>