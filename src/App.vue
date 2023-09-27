<template>
  <div id="app">
    <TrilobiteList :items="dataFromApi"></TrilobiteList>
  </div>
</template>

<script setup>
import {ref } from 'vue';
import uniqueId from 'lodash.uniqueid'
import TrilobiteList from './components/TrilobiteList.vue';

const dataFromApi = ref([]);
async function getData() {
  const response = await fetch('https://api.gbif.org/v1/species/search?rank=SPECIES&highertaxon_key=9273948&status=ACCEPTED');
  const result = await response.json();
  dataFromApi.value = result['results'].map((species) => {
    return {
          label: species['canonicalName'],
          done: Math.random() < 0.5,
          id: uniqueId("todo-")
    }
  });
}
getData()


</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
