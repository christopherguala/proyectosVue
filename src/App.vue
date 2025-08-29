<script setup>
// const saludo = 'hola mundo';
// const styleColor = 'color: blue;';
//arreglos
// const arregloColor = ['red', 'green', 'blue'];
// const activo = true;
// const frutas = ['manzana', 'pera', 'sandia'];
// const objetoFrutas = [
//   {id: 1, nombre: 'manzana', color: 'red', precio: 10},
//   {id: 2, nombre: 'pera', color: 'green', precio: 20},
//   {id: 3, nombre: 'sandia', color: 'yellow', precio: 30},
//   ]
import UserList from './components/UserList.vue'
</script>



<template>
  <!-- <h1>{{ saludo }}</h1>
  <h2 :style="styleColor"> estilo</h2>
  <h2 :style="{ color: arregloColor[1]}">{{ arregloColor }}</h2>
  <h2>{{ activo ? 'activo' : 'inactivo' }}</h2> -->
  <!-- Directivas -->
  <!-- v-if -->
  <!-- <h2 v-if="activo">activo</h2>
  <h2 v-else>inactivo</h2> -->
  <!-- v-show -->
  <!-- <h2 v-show="activo">activo</h2>
  <h2 v-show="!activo">inactivo</h2> -->
  <!-- v-for -->
  <!-- <ul>
    <li v-for="(fruta, index) in frutas" :key="index">
      {{ index }} - {{ fruta }}
    </li>
  </ul> -->
  <!-- v-for array objetos -->
  <!-- <ul>
    <li v-for="(fruta, index) in objetoFrutas" :key="index">
      {{ fruta.id }} - {{ fruta.nombre }} - {{ fruta.color }} - {{ fruta.precio }}
    </li>
  </ul> -->

  <UserList />
</template>



<style>
/* h1 {
  color: red;
} */
</style>