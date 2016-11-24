<template>
  <div>
    <h1>Pokemons</h1>
    <table class="table">
      <thead>
        <tr>
          <th>Name</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="pokemon in pokemons">
          <td><a :href="pokemon.url" v-on:click.prevent="selectPokemon(pokemon.url)">{{ pokemon.name }}</a></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'pokemon-list',
  props: ['pokemons', 'selectPokemon'],
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
