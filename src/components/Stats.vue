<template>
  <div>
    <h1>Stats</h1>
    <table class="table">
      <thead>
        <tr>
          <th>Name</th>
          <th>Effort</th>
          <th>Base</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="stat in selectedPokemon.stats">
          <td>{{ stat.stat.name }}</td>
          <td>{{ stat.effort }}</td>
          <td>{{ stat.base_stat }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>

export default {
  name: 'stats',
  props: ['selectedPokemon'],
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
