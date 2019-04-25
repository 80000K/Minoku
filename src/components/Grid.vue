<template>
  <div class="grid">
    <Box v-for="index in 9" :key="index" :value="board[index - 1]"> </Box>
  </div>
</template>

<script>
import Box from "./Box.vue";
export default {
  components: {
    Box
  },
  props: ["board"]
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.grid {
  width: 150px;
  display: grid;
  flex-wrap: wrap;
  grid-template-columns: repeat(3, 1fr);
  justify-content: space-around;
  margin: 1px;
}
</style>
