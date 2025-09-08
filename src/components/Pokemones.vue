

<template>
  <div class="container mt-4">
    <div class="mb-3">
      <input
        v-model="searchQuery"
        type="text"
        class="form-control"
        placeholder="buscar Pokémon por nombre"
        @input="validateSearch"
      />
    </div>

    <div class="row">
      <div
        class="col-md-4 mb-3"
        v-for="pokemon in filteredPokemons"
        :key="pokemon.id"
      >
        <div class="card">
          <img
            :src="pokemon.imagen"
            class="card-img-top"
            :alt="pokemon.nombre"
          />
          <div class="card-body">
            <h5 class="card-title text-capitalize">{{ pokemon.nombre }}</h5>
          </div>
        </div>
      </div>
    </div>

    <div v-if="filteredPokemons.length === 0" class="alert alert-warning mt-3">
      El pokémon que desea buscar no existe.
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

const pokemones = ref([
  { id: '1', nombre: 'pikachu', imagen: 'https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/025.png' },
  { id: '2', nombre: 'kakuna', imagen: 'https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/014.png' },
  { id: '3', nombre: 'beedrill', imagen: 'https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/015.png' },
  { id: '4', nombre: 'metapod', imagen: 'https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/011.png' },
  { id: '5', nombre: 'rattata', imagen: 'https://www.pokemon.com/static-assets/content-assets/cms2/img/pokedex/full/019.png' },
])

const searchQuery = ref('')
const filteredPokemons = computed(() => {
  return pokemones.value.filter((pokemon) =>
    pokemon.nombre.toLowerCase().includes(searchQuery.value.toLowerCase())
  )
})
</script>