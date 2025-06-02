<script setup>
import Lista from "./components/Lista.vue";
import Tareas from "./components/Tareas.vue";
import DimensionComponente from "./components/DimensionComponente.vue";

import { ref } from "vue";

const currentComponent = ref("Lista");

const componentes = {
  Lista: Lista,
  Tareas: Tareas,
  Dimensiones: DimensionComponente,
};
</script>

<template>
  <div>
    <h1>Trabajo Práctico N° 4</h1>
    <button @click="currentComponent = 'Lista'">Ver Lista</button>
    <button @click="currentComponent = 'Tareas'">Ver Tareas</button>
    <button @click="currentComponent = 'Dimensiones'">Ver Dimensiones</button>

    <component :is="componentes[currentComponent]" />
  </div>
</template>
<style></style>
