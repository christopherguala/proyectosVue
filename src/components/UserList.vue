<script setup>
import { ref } from 'vue'
    let usuarios = ref([]);
    class Usuario {
        constructor(id, nombre, edad, rut) {
            this.id = id;
            this.nombre = nombre;
            this.edad = edad;
            this.rut = rut;
            //se elimina el this push o la pagina se iba a blanco xd
        }
    }

    usuarios.value.push( // ahora se puchea con .value
    new Usuario(1, "Juan", 20, "12.345.678-9"),
    new Usuario(2, "Pedro", 25, "23.456.789-0"),
    new Usuario(3, "Maria", 30, "34.567.890-1"),
    new Usuario(4, "Luis", 35, "45.678.901-2"),
    new Usuario(5, "Ana", 40, "56.789.012-3")
)

    function crearUsuario() {
    const nombre = prompt('Ingrese nombre:')
    if (!nombre) return

    const edad = prompt('Ingrese edad:')
    if (!edad || isNaN(edad)) return alert('Edad no válida')

    const rut = prompt('Ingrese RUT:')
    if (!rut) return

    const nuevoId = 
        usuarios.value.length > 0
            ? Math.max(...usuarios.value.map((u) => u.id)) + 1
            : 1

    // Crear e insertar usuario
    const nuevoUsuario = new Usuario(nuevoId, nombre, parseInt(edad), rut)
    usuarios.value.push(nuevoUsuario)
}

</script>
<template> 

    <div class="container mt-4">
        <button class="btn btn-primary mb-3" @click="crearUsuario">
      Agregar Usuario
    </button>
    <table class="table table-dark table-striped table-bordered table-hover">
      <thead>
        <tr>
          <th>ID</th>
          <th>Nombre</th>
          <th>Edad</th>
          <th>Rut</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="usuario in usuarios" :key="usuario.id">
          <td>{{ usuario.id }}</td>
          <td>{{ usuario.nombre }}</td>
          <td>{{ usuario.edad }}</td>
          <td>{{ usuario.rut }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>