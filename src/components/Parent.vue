<template>
  <div class="hello-world">
    <Child></Child>
    <div>{{ thisColor }}</div>
  </div>
</template>

<script>
import Child from "./Child";
export default {
  name: "HelloWorld",
  props: ["color"],
  data() {
    return { thisColor: this.color };
  },
  methods: {
    // getThis() {
    //   console.log(this.color);
    //   console.log(this.thisColor);
    // },
    // handleClick() {
    //   this.$emit("change-color");
    // },
  },
  watch: {
    color: function (val, oldVal) {
      this.thisColor = val;
    },
  },
  created() {
    //this.getThis();
  },
  components: {
    Child,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
