<template>
  <div class="text-center" >
    <div v-if="selectedPokemon.name">
      <img :src="pokemonAnimated" alt="No pokemon selected">
      <h1>{{ selectedPokemon.name }}</h1>
    </div>
    <div v-else>
      <p>Please select a pokemon from the list</p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'pokemon',
  props: ['selectedPokemon'],
  computed: {
    pokemonAnimated() {
      return `http://pokegifs.surge.sh/${this.selectedPokemon.id}.gif`;
    },
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
