<template>
  <div>
    <div class="col-md-3">
      <pokemon-list v-bind:pokemons="pokemons" :select-pokemon="selectPokemon"></pokemon-list>
    </div>
    <div class="col-md-9">
      <pokemon v-bind:selected-pokemon="selectedPokemon"></pokemon>
      <stats v-bind:selected-pokemon="selectedPokemon"></stats>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import PokemonList from './PokemonList';
import Pokemon from './Pokemon';
import Stats from './Stats';

export default {
  name: 'pokemons',
  components: {
    PokemonList,
    Pokemon,
    Stats,
  },
  created() {
    axios.get('http://pokeapi.co/api/v2/pokemon')
      .then((response) => {
        this.pokemons = response.data.results;
      });
  },
  methods: {
    selectPokemon(url) {
      axios.get(url)
        .then((response) => {
          this.selectedPokemon = response.data;
        });
    },
  },
  data() {
    return {
      pokemons: [],
      selectedPokemon: {
        id: '',
        name: '',
        sprites: {
          front_default: '',
        },
        stats: [],
      },
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
