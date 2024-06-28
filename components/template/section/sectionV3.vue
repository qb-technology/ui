<script setup lang='ts'>
import type { PropType } from 'vue';
import type { SectionText } from "~/types"

defineProps({
    sectionText: Object as PropType<SectionText>,
    layoutOrientation: String as PropType<'left' | 'right' | 'center'>,
    p: {
        type: String,
        default: 'py-24 sm:py-32'
    }
})
</script>

<template>
    <div class="gap-12"
        :class="[layoutOrientation == 'center' ? 'grid' : 'flex items-center', layoutOrientation == 'right' && 'flex-row-reverse', p]">
        <div :class="[layoutOrientation == 'center' ? 'basis-full' : 'basis-1/2']">
            <TextV2 :section-text="sectionText" :orientation="layoutOrientation" />
        </div>
        <div :class="[layoutOrientation == 'center' ? 'basis-full' : 'basis-1/2']">
            <slot />
        </div>
    </div>
</template>