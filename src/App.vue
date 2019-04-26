<template>
  <div id="app">
    <Main/>
  </div>
</template>

<script>
import Main from "./components/Main.vue";
import "bootstrap";

export default {
  name: "app",
  components: {
    Main
  }
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
}

@import "../node_modules/bootstrap/dist/css/bootstrap.css";
@import "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css";
</style>