//línea 7: $emit -> evento que le vamos a emitir al componente padre. El primer argumento es el nombre del evento que queremos disparar (obligatorio), el segundo
<template>
  <div class="options-container">
    <ul>
      <li v-for="pokemon in pokemons" 
      :key="pokemon.id"
      @click="$emit('selected-pokemon', pokemon.id)"> 
      {{ pokemon.name }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    pokemons: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
ul {
  list-style-type: none;
}
li {
  background-color: white;
  border-radius: 5px;
  border: 1px solid rgba(0, 0, 0, 0.2);
  cursor: pointer;
  margin-bottom: 10px;
  width: 250px;
}

li:hover {
  background-color: rgba(0, 0, 0, 0.05);
}

.options-container {
  display: flex;
  justify-content: center;
}
</style>