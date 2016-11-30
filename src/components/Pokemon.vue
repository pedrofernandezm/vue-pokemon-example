<template>
  <div class="text-center" >
    <template v-if="loading">
      <spinner :spin="spin"></spinner>
    </template>
    <template v-else>
      <div v-if="selectedPokemon.name">
        <img :src="pokemonAnimated" :alt="selectedPokemon.name">
        <h1>{{ selectedPokemon.name }}</h1>
      </div>
      <div v-else>
        <p>Please select a pokemon from the list</p>
      </div>
      <stats v-bind:selected-pokemon="selectedPokemon"></stats>
    </template>
  </div>
</template>

<script>

import Spinner from './Spinner';
import Stats from './Stats';

export default {
  name: 'pokemon',
  props: ['selectedPokemon', 'loading'],
  components: {
    Spinner,
    Stats,
  },
  computed: {
    pokemonAnimated() {
      return `http://pokemongifs.surge.sh/${this.selectedPokemon.name}.gif`;
    },
  },
  data() {
    return {
      spin: 'pacman',
    };
  },

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
