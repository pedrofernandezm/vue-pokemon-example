<template>
  <div class="spinner">
    <pacman-loader></pacman-loader>
  </div>
</template>

<script>

import PacmanLoader from 'vue-spinner/src/PacmanLoader';

export default {
  name: 'spinner',
  components: {
    PacmanLoader,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .spinner{
    display: flex;
    align-items: center;
    height: 100vh;
    justify-content: center;
  }
</style>
