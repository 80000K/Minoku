<template>
  <div
    class="box"
    v-bind:style="{ background: colors[value] }"
    v-on:click="handleClick"
  >
    <span> {{ value !== 0 ? value : "" }} </span>
  </div>
</template>

<script>
export default {
  props: ["value"],
  data: () => {
    return {
      locked: false,
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
  },
  mounted() {
    this.locked = this.value !== 0;
  },
  methods: {
    handleClick() {
      if (!this.locked) {
        this.value++;
        if (this.value > 9) this.value = 1;
      }
    }
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
  align-items: center;
  justify-content: center;
  border: 1px solid #999;
  span {
    display: block;
    // align-self: center;
    // color: #fff;
  }
}
</style>
