<script setup>
import { ref, onMounted } from "vue";

const elementos = ref([]);

onMounted(() => {
  setTimeout(() => {
    // Simula datos cargados luego de 3 segundos
    elementos.value = ["Elemento 1", "Elemento 2", "Elemento 3"];
  }, 3000);
});
</script>

<template>
  <div>
    <h2>Lista de elementos</h2>
    <ul>
      <li v-for="(item, index) in elementos" :key="index">{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped>
h2 {
  color: #888;
}
</style>
