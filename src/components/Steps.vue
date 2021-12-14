<template>
  <template v-if="step === 'new'">
    <slot name="new" :actions="{ confirmStepHandler }" />
  </template>
  <template v-if="step === 'confirm'">
    <slot name="confirm" :actions="{ newStepHandler, completeStepHandler }" />
  </template>
  <template v-if="step === 'complete'">
    <slot name="complete" :actions="{ newStepHandler }" />
  </template>
</template>

<script lang="ts">
type Step = "new" | "confirm" | "complete"
import { ref } from "vue"

export default {
  setup() {
    const step = ref<Step>("new")

    const newStepHandler = () => {
      step.value = "new"
    }

    const confirmStepHandler = () => {
      step.value = "confirm"
    }

    const completeStepHandler = () => {
      step.value = "complete"
    }

    return {
      step,
      newStepHandler,
      confirmStepHandler,
      completeStepHandler,
    }
  },
}
</script>
