<template>
  <div>
    <h1>Masukan Kata-Kata</h1>
    <input v-model="text" placeholder="Type here">
    <button @click="applyFilter('uppercase')">Uppercase</button>
    <button @click="applyFilter('lowercase')">Lowercase</button>
    <p>{{ filteredText }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const text = ref('')

const filteredText = computed(() => {
  if (filter.value === 'uppercase') {
    return text.value.toUpperCase(); 
  } else if (filter.value === 'lowercase') {
    return text.value.toLowerCase(); 
  } else {
    return text.value; 
  }
})

const filter = ref('');

const applyFilter = (selectedFilter) => {
  filter.value = selectedFilter;
}
</script>
