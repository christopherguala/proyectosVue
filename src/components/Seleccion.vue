<template>
  <div>
    <h2>Tipo de estudios</h2>

    <div>
      <input type="radio" id="primarios" value="Primarios" v-model="estudios">
      <label for="primarios">Primarios</label>

      <input type="radio" id="secundarios" value="Secundarios" v-model="estudios">
      <label for="secundarios">Secundarios</label>

      <input type="radio" id="terciarios" value="Terciarios" v-model="estudios">
      <label for="terciarios">Terciarios</label>

      <input type="radio" id="universitarios" value="Universitarios" v-model="estudios">
      <label for="universitarios">Universitarios</label>
    </div>

    <p>Estudios seleccionados: <strong>{{ estudios }}</strong></p>

    <hr>

    <h2>Selecciona un día de la semana</h2>

    <select v-model="diaSeleccionado">
      <option disabled value="">Seleccione un día</option>
      <option>Lunes</option>
      <option>Martes</option>
      <option>Miércoles</option>
      <option>Jueves</option>
      <option>Viernes</option>
      <option>Sábado</option>
      <option>Domingo</option>
    </select>

    <p>Día seleccionado: <strong>{{ diaSeleccionado }}</strong></p>
  </div>
</template>

<script>
export default {
  name: 'Seleccion',
  data() {
    return {
      estudios: 'Universitarios', // valor por defecto
      diaSeleccionado: ''
    };
  }
}
</script>

<style scoped>
h2 {
  margin-top: 20px;
}

label {
  margin-right: 15px;
}
</style>