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
    :class="[layoutOrientation == 'center' && 'justify-items-center', layoutOrientation == 'right' && 'justify-items-end', layoutOrientation == 'left' && 'justify-between', p, layoutOrientation == 'center' ? 'grid' : 'flex']">
    <div>
      <Text :section-text="sectionText" :orientation="layoutOrientation" />
    </div>
    <div>
      <slot />
    </div>
  </div>
</template>