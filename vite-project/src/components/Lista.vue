<script setup>
import { ref, onMounted } from "vue";
import profesionesData from "../resources/profesiones";

const profesiones = ref([]);

onMounted(() => {
  setTimeout(() => {
    profesiones.value = profesionesData;
  }, 3000);
});
</script>

<template>
  <div>
    <h2>Lista de profesiones</h2>
    <ul>
      <li v-for="item in profesiones" :key="item.id">
        <strong>{{ item.nombre }}</strong
        >: {{ item.descripcion }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
h2 {
  color: #888;
}
</style>
