<script>

import PacmanLoader from 'vue-spinner/src/PacmanLoader';
import BounceLoader from 'vue-spinner/src/BounceLoader';

export default {
  name: 'spinner',
  components: {
    PacmanLoader,
    BounceLoader,
  },
  render: function a(createElement) {
    return createElement(
      'div',
      {
        class: {
          spinner: true,
        },
      },
      [createElement(`${this.spin}-loader`)]
    );
  },
  props: ['spin'],
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
