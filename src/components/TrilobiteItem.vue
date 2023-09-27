<template>
  <div class="trilobite">
    <input type="checkbox" :id="props.id" :checked="props.done" />
    <label :for="props.id">{{ props.label }}</label>
  </div>
</template>

<script setup>
import {defineProps} from 'vue';
const props = defineProps({
  label: String,
  done: Boolean,
  id: String
})
</script>

<style scoped>
</style>
