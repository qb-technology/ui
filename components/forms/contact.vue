<script setup lang="ts">
import type { FormError, FormSubmitEvent } from '#ui/types'

const state = reactive({
  email: undefined,
  name: undefined,
  msg: undefined,
})

const validate = (state: any): FormError[] => {
  const errors = []
  if (!state.email) errors.push({ path: 'email', message: 'Required' })
  if (!state.name) errors.push({ path: 'name', message: 'Required' })
  if (!state.msg) errors.push({ path: 'message', message: 'Required' })
  return errors
}
const emits = defineEmits(['submit'])
async function onSubmit(event: FormSubmitEvent<any>) {
  // Do something with data
  emits('submit', event.data)
}
</script>

<template>
  <UForm :validate="validate" :state="state" class="space-y-4" @submit="onSubmit">
    <UFormGroup label="Name" name="name">
      <UInput v-model="state.name" />
    </UFormGroup>
    <UFormGroup label="Email" name="email">
      <UInput v-model="state.email" />
    </UFormGroup>
    <UFormGroup label="Message" name="message">
      <UTextarea v-model="state.msg" autoresize :maxrows="5" />
    </UFormGroup>



    <UButton type="submit" size="sm" block>
      Send
    </UButton>
  </UForm>
</template>
