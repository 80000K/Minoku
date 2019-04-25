<template>
  <div class="box" v-bind:style="{ background: colors[value] }">
    <span> {{ value }} </span>
  </div>
</template>

<script>
export default {
  props: ["value"],
  data: () => {
    return {
      colors: [
        "#fff",
        "#F5B7B1",
        "#C39BD3",
        "#85C1E9",
        "#A3E4D7",
        "#F7DC6F",
        "#F0B27A",
        "#F0F3F4",
        "#B2BABB",
        "#1F618D"
      ]
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.box {
  width: 50px;
  height: 50px;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border: 1px solid #999;
}
</style>
