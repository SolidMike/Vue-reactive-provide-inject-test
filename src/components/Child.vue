<template>
  <button @click="handleChangeColor">{{ color }}</button>
</template>

<script>
export default {
  name: "Child",
  props: {},
  computed: {
    color() {
      return this.getColor();
    },
  },
  // methods: {
  //   handleClick() {
  //     this.$emit("click");
  //   },
  // },
  inject: ["handleChangeColor", "getColor"],
};
</script>

<style scoped>
</style>