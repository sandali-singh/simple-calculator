<template>
  <div id="app">
    <calculator></calculator>
  </div>
</template>

<script>
import calculator from "./components/calculator.vue";
export default {
  name: "App",
  components: {
    calculator,
  },
};
</script>

<style>
body {
  margin: 0;
}
#app {
  height: 100vh;
  overflow: hidden;
  background-image: url("../public/bold.png");
  background-position-x: 20%;
}
</style>
