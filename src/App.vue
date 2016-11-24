<template>
  <div id="app" class="row">
    <pokemons></pokemons>
  </div>
</template>

<script>
import Pokemons from './components/Pokemons';

export default {
  name: 'app',
  components: {
    Pokemons,
  },
};
</script>

<style scoped>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
