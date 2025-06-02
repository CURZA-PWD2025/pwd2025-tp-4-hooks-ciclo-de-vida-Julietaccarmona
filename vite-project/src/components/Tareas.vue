<script setup>
import { ref, onBeforeUpdate, onUpdated } from 'vue'

const tareas = ref(['Estudiar', 'Leer'])
const nuevaTarea = ref('')
let tareasAnteriores = []

onBeforeUpdate(() => {
  console.log("Lista aún no modificada")
  tareasAnteriores = [...tareas.value]
})

onUpdated(() => {
  console.log("Lista modificada")
})

const agregarTarea = () => {
  if (nuevaTarea.value) {
    tareas.value.push(nuevaTarea.value)
    nuevaTarea.value = ''
  }
}
</script>

<template>
  <div>
    <h2>Mis Tareas</h2>
    <input v-model="nuevaTarea" placeholder="Nueva tarea" />
    <button @click="agregarTarea">Agregar</button>
    <ul>
      <li
        v-for="(tarea, index) in tareas"
        :key="index"
        :style="{ color: tareasAnteriores.includes(tarea) ? 'blue' : 'black' }"
      >
        {{ tarea }}
      </li>
    </ul>
  </div>
</template>
