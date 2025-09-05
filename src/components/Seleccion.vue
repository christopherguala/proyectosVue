<template> <!--no entiendo por que me sale sugerencia amarilla en el < revisar luego xd  -->
  <div class="d-flex justify-content-center align-items-center min-vh-100">
    <div
      class="p-4 text-white rounded shadow w-50 box-color rounded-4"
      style="min-width: 320px"
    >
      <h2 class="text-dark">Tipo de estudios</h2>

      <div class="text-dark d-flex gap-3">
        <input
          type="radio"
          id="electricidad"
          value="Electricidad"
          v-model="estudios"
        />
        <label for="electricidad">Electricidad</label>

        <input
          type="radio"
          id="programacion"
          value="Programacion"
          v-model="estudios"
        />
        <label for="programacion">Programacion</label>

        <input
          type="radio"
          id="pedagogia"
          value="Pedagogia"
          v-model="estudios"
        />
        <label for="pedagogia">Pedagogia</label>

        <input
          type="radio"
          id="administracion"
          value="Administracion"
          v-model="estudios"
        />
        <label for="administracion">Administracion</label>
      </div>

      <p class="text-dark">
        Estudio seleccionado: <strong>{{ estudios }}</strong>
      </p>

      <hr /> <!-- lineam vacia para mi estilo nomas -->

      <h2 class="text-dark">Selecciona un día de la semana</h2>

      <select v-model="diaSeleccionado" class="form-select">
        <option disabled value="">Seleccione un día</option>
        <option>Lunes</option>
        <option>Martes</option>
        <option>Miércoles</option>
        <option>Jueves</option>
        <option>Viernes</option>
        <option>Sábado</option>
        <option>Domingo</option>
      </select>

      <p class="text-dark">
        Día seleccionado: <strong>{{ diaSeleccionado }}</strong>
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const estudios = ref("");
const diaSeleccionado = ref("");
</script>

<style scoped>
* {
  font-family: "Poppins", sans-serif;
}
.box-color {
  background-color: bisque;
  color: black;
}
</style>
