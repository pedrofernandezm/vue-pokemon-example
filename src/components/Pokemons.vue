<template>
  <div>
    <div class="col-md-3">
      <pokemon-list v-bind:pokemons="pokemons" :select-pokemon="selectPokemon"></pokemon-list>
    </div>
    <div class="col-md-9">
      <pokemon v-bind:selected-pokemon="selectedPokemon" v-bind:loading="loading"></pokemon>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import PokemonList from './PokemonList';
import Pokemon from './Pokemon';

export default {
  name: 'pokemons',
  components: {
    PokemonList,
    Pokemon,
  },
  created() {
    axios.get('http://pokeapi.co/api/v2/pokemon')
      .then((response) => {
        this.pokemons = response.data.results;
      });
  },
  methods: {
    selectPokemon(url) {
      this.loading = true;
      this.selectedPokemon = {};
      axios.get(url)
        .then((response) => {
          this.selectedPokemon = response.data;
          this.loading = false;
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
      loading: false,
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
