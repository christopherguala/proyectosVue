<script setup>
import { ref } from "vue";

let personajes = ref([
  { id: 1, nombre: "frodo", descripcion: "el prota debio ser sam :v" },
  { id: 2, nombre: "fuke skywalker", descripcion: "su papa le debe pension" },
  { id: 3, nombre: "iron Man", descripcion: "un cuate en un mecha" },
  { id: 4, nombre: "naruto", descripcion: "yo antes era como tu " },
  { id: 5, nombre: "motapod", descripcion: "motapod endurecete"} //solo algunos entenderan xd
]);

let mostrarTabla = ref(false);
</script>

<template>
  <div class="container mt-4">
    <h3>Lista de Personajes</h3>

    <button class="btn btn-primary mb-3" @click="mostrarTabla = !mostrarTabla">
      {{ mostrarTabla ? 'Ocultar Personajes' : 'Mostrar Personajes' }}
    </button>

    <table v-if="mostrarTabla" class="table table-dark table-striped table-bordered table-hover">
      <thead>
        <tr>
          <th>ID</th>
          <th>Nombre</th>
          <th>Descripción</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="personaje in personajes" :key="personaje.id">
          <td>{{ personaje.id }}</td>
          <td>{{ personaje.nombre }}</td>
          <td>{{ personaje.descripcion }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
.container {
  background-color: bisque;
  padding: 20px;
  border-radius: 10px;
}
</style>