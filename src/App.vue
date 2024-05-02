<template>
  <div>
    <input v-model="text" placeholder="Type here">
    <!-- Tombol untuk mengubah teks menjadi uppercase -->
    <button @click="applyFilter('uppercase')">Uppercase</button>
    <!-- Tombol untuk mengubah teks menjadi lowercase -->
    <button @click="applyFilter('lowercase')">Lowercase</button>
    <!-- Menampilkan hasil text yang telah difilter -->
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
