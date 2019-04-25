<template>
  <div id="app">
    <Grid
      v-for="index in 9"
      :key="index"
      :board="convertMatrix(board)[index - 1]"
    />
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
      board: blink(20)
    };
  },
  components: {
    Grid
  },
  methods: {
    convertMatrix(temp) {
      let board = new Array();
      board[0] = [
        temp[0][0],
        temp[0][1],
        temp[0][2],
        temp[1][0],
        temp[1][1],
        temp[1][2],
        temp[2][0],
        temp[2][1],
        temp[2][2]
      ];

      board[1] = [
        temp[0][3],
        temp[0][4],
        temp[0][5],
        temp[1][3],
        temp[1][4],
        temp[1][5],
        temp[2][3],
        temp[2][4],
        temp[2][5]
      ];
      board[2] = [
        temp[0][6],
        temp[0][7],
        temp[0][8],
        temp[1][6],
        temp[1][7],
        temp[1][8],
        temp[2][6],
        temp[2][7],
        temp[2][8]
      ];
      board[3] = [
        temp[3][0],
        temp[3][1],
        temp[3][2],
        temp[4][0],
        temp[4][1],
        temp[4][2],
        temp[5][0],
        temp[5][1],
        temp[5][2]
      ];
      board[4] = [
        temp[3][3],
        temp[3][4],
        temp[3][5],
        temp[4][3],
        temp[4][4],
        temp[4][5],
        temp[5][3],
        temp[5][4],
        temp[5][5]
      ];
      board[5] = [
        temp[3][6],
        temp[3][7],
        temp[3][8],
        temp[4][6],
        temp[4][7],
        temp[4][8],
        temp[5][6],
        temp[5][7],
        temp[5][8]
      ];
      board[6] = [
        temp[6][0],
        temp[6][1],
        temp[6][2],
        temp[7][0],
        temp[7][1],
        temp[7][2],
        temp[8][0],
        temp[8][1],
        temp[8][2]
      ];
      board[7] = [
        temp[6][3],
        temp[6][4],
        temp[6][5],
        temp[7][3],
        temp[7][4],
        temp[7][5],
        temp[8][3],
        temp[8][4],
        temp[8][5]
      ];
      board[8] = [
        temp[6][6],
        temp[6][7],
        temp[6][8],
        temp[7][6],
        temp[7][7],
        temp[7][8],
        temp[8][6],
        temp[8][7],
        temp[8][8]
      ];
      return board;
    }
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
