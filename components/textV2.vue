<script setup lang='ts'>
import type { PropType } from "vue";
import type { SectionText } from "@/types"
defineProps({

    sectionText: {
        type: Object as PropType<SectionText>,
        default: {
            h1: 'Purus sagittis fringilla arcu neque.',
            h2: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Bibendum amet at molestie mattis.',
            p: 'Rhoncus morbi et augue nec, in id ullamcorper at sit. Condimentum sit nunc in eros scelerisque sed. Commodo in viverra nunc, ullamcorper ut. Non, amet, aliquet scelerisque nullam sagittis, pulvinar. Fermentum scelerisque sit consectetur hac mi. Mollis leo eleifend ultricies purus iaculis.',
            caption: {
                label: 'Caption',
                variant: 'soft'
            }
        }
    },
    orientation: {
        type: String as PropType<'left' | 'right' | 'center'>,
        // default: 'center'
    }
})
</script>

<template>
    <div class="space-y-12" :class="[orientation == 'center' && 'text-center', orientation == 'right' && 'text-right']">
        <div class="space-y-2">
            <slot name="caption">
                <UBadge v-if="Boolean(sectionText.caption)" variant="soft" v-bind="sectionText.caption" />
            </slot>
            <slot name="h1">
                <h1 v-if="Boolean(sectionText.h1)" class="text-6xl font-bold leading-tight">{{ sectionText.h1 }}</h1>
            </slot>
            <slot v-if="Boolean(sectionText.h2)" name="h2">
                <h2 class="text-2xl md:text-3xl lg:text-5xl font-bold leading-tight">{{ sectionText.h2 }}</h2>
            </slot>

        </div>
        <slot name="p">
            <p v-if="Boolean(sectionText.p)" class="text-lg">{{ sectionText.p }}</p>
        </slot>
    </div>
</template>