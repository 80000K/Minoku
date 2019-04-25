<template>
  <div id="app">
    <Grid v-for="index in 9" :key="index" :board="puzzle[index - 1]" />
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";
// eslint-disable-next-line no-unused-vars
const { matrix, blink, checkMatrix } = require("sudoku-matrix");

export default {
  name: "app",
  data: () => {
    return {
      puzzle: blink(20)
    };
  },
  components: {
    Grid
  }
};
</script>

<style lang="scss" scoped>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin-top: 60px;
  display: grid;

  grid-template-columns: repeat(3, 1fr);
  justify-content: space-around;
  width: 475px;
}
</style>
