<script setup>
import { ref } from "vue";

let usuarios = ref([]);

let form = ref({
  nombre: "",
  correo: "",
  edad: "",
  rut: ""
});

let mostrarTabla = ref(false);

class Usuario {
  constructor(id, nombre, correo, edad, rut) {
    this.id = id;
    this.nombre = nombre;
    this.correo = correo;
    this.edad = edad;
    this.rut = rut;
  }
}

usuarios.value.push(
  new Usuario(1, "Juan", "juan@mail.com", 20, "12.345.678-9"),
  new Usuario(2, "Pedro", "pedro@mail.com", 25, "23.456.789-0"),
  new Usuario(3, "Maria", "maria@mail.com", 30, "34.567.890-1"),
  new Usuario(4, "Luis", "luis@mail.com", 35, "45.678.901-2"),
  new Usuario(5, "Ana", "ana@mail.com", 40, "56.789.012-3")
);

function crearUsuario() {
  if (!form.value.nombre || !form.value.correo || !form.value.edad || !form.value.rut) {
    return alert("Por favor complete todos los campos");
  }

  if (isNaN(form.value.edad)) {
    return alert("La edad debe ser un número");
  }

  const nuevoId =
    usuarios.value.length > 0
      ? Math.max(...usuarios.value.map((u) => u.id)) + 1
      : 1;

  const nuevoUsuario = new Usuario(
    nuevoId,
    form.value.nombre,
    form.value.correo,
    parseInt(form.value.edad),
    form.value.rut
  );

  usuarios.value.push(nuevoUsuario);
  limpiarFormulario();
}

function limpiarFormulario() {
  form.value = {
    nombre: "",
    correo: "",
    edad: "",
    rut: ""
  };
}
</script>

<template>
  <div class="container mt-4">

    <div class="card p-3 mb-4 formulario">
      <h4>Agregar Usuario</h4>
      <form @submit.prevent="crearUsuario">
        <div class="mb-3">
          <label class="form-label">Nombre</label>
          <input v-model="form.nombre" type="text" class="form-control" placeholder="Ingrese nombre" />
        </div>
        <div class="mb-3">
          <label class="form-label">Correo</label>
          <input v-model="form.correo" type="email" class="form-control" placeholder="Ingrese correo" />
        </div>
        <div class="mb-3">
          <label class="form-label">Edad</label>
          <input v-model="form.edad" type="number" class="form-control" placeholder="Ingrese edad" />
        </div>
        <div class="mb-3">
          <label class="form-label">RUT</label>
          <input v-model="form.rut" type="text" class="form-control" placeholder="Ingrese RUT" />
        </div>
        <button type="submit" class="btn btn-success me-2">Agregar</button>
        <button type="button" class="btn btn-secondary" @click="limpiarFormulario">Limpiar</button>
      </form>
    </div>

    <button class="btn btn-primary mb-3" @click="mostrarTabla = !mostrarTabla">
      {{ mostrarTabla ? 'Ocultar Información' : 'Mostrar Información' }}
    </button>

    <table v-if="mostrarTabla" class="table table-dark table-striped table-bordered table-hover">
      <thead>
        <tr>
          <th>ID</th>
          <th>Nombre</th>
          <th>Correo</th>
          <th>Edad</th>
          <th>Rut</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="usuario in usuarios" :key="usuario.id">
          <td>{{ usuario.id }}</td>
          <td>{{ usuario.nombre }}</td>
          <td>{{ usuario.correo }}</td>
          <td>{{ usuario.edad }}</td>
          <td>{{ usuario.rut }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
.formulario {
  background-color:bisque
}
</style>