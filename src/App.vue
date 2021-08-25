<template>
  <div id="app">
    <Parent :style="'background-color:' + color" :color="color" />
  </div>
</template>

<script>
import Parent from "./components/Parent";

export default {
  name: "App",
  components: {
    Parent,
  },
  data: () => ({
    color: "blue",
  }),
  // data: function () {
  //   return {
  //     color: "blue",
  //   };
  // },
  methods: {
    handleChangeColor() {
      this.color = this.color === "red" ? "blue" : "red";
      console.log(this.color);
    },
  },
  // provide: function () {
  //   return { handleChangeColor: this.handleChangeColor, color: this.color };
  // },
  provide() {
    return {
      getColor: () => this.color,
      handleChangeColor: this.handleChangeColor,
    };
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  width: 500px;
  height: 500px;
}
</style>
