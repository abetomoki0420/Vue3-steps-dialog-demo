<template>
  <Steps>
    <template #new="scopedProps">
      <h1>This is new Page</h1>
      <button @click="scopedProps.actions.confirmStepHandler()">confirm</button>
    </template>
    <template #confirm="scopedProps">
      <h1>This is Confirm Page</h1>
      <div>are you ok?</div>
      <button @click="scopedProps.actions.newStepHandler()">prev</button>
      <button @click="scopedProps.actions.completeStepHandler()">next</button>
    </template>
    <template #complete="scopedProps">
      <h1>This is Complete Page</h1>
      <div>Conguratiration!</div>
      <button @click="scopedProps.actions.newStepHandler()">back to new</button>
    </template>
  </Steps>
</template>

<script lang="ts">
import Steps from "./Steps.vue"
export default {
  components: { Steps },
  setup() {},
}
</script>
