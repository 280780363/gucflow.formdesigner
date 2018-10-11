<template>
  <div id="app">
    <FormDesiner msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import FormDesiner from "./components/FormDesiner.vue";
export default {
  name: "app",
  components: {
    FormDesiner
  }
};
</script>

<style lang="less">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
