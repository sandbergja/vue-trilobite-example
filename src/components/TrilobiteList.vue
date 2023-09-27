<template>
  <div>
    <h1>Trilobite List</h1>
    <ul>
      <li v-for="listItem in props.items" :key="listItem.id">
        <TrilobiteItem :label="listItem.label"
                        :done="listItem.done"
                        :id="listItem.done"></TrilobiteItem>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';
import TrilobiteItem from './TrilobiteItem.vue';
  const props = defineProps({
  items: Array
})
</script>

<style>
</style>
