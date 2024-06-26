<script setup lang='ts'>
import type { PropType } from 'vue';
import type { SectionText } from "~/types"

defineProps({
    sectionText: Object as PropType<SectionText>,
    layoutOrientation: String as PropType<'left' | 'right' | 'center'>,
    p: {
        type: String,
        default: 'py-24 sm:py-32 md:py-40'
    }
})
</script>

<template>
    <div class="grid gap-12"
        :class="[layoutOrientation == 'center' && 'justify-items-center', layoutOrientation == 'right' && 'justify-items-end', p]">
        <Text :section-text="sectionText" :orientation="layoutOrientation" />
        <slot />
    </div>
</template>