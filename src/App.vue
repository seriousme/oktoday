<template>
  <div id="app">
    <div class="container" style="max-width: 800px">
      <nav class="navbar navbar-expand-lg navbar-dark bg-info">
        <a class="navbar-brand" href="#">OK Today</a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav mr-auto"></ul>
          <ul class="navbar-nav">
            <li class="nav-item" v-bind:class="{ active: (page=='Input') }">
              <span class="nav-link" v-on:click="page = 'Input'">Invoer</span>
            </li>
            <li class="nav-item" v-bind:class="{ active: (page=='Overview')}">
              <span class="nav-link" v-on:click="page = 'Overview'">Overzicht</span>
            </li>
          </ul>
        </div>
      </nav>
      <Input v-if="page === 'Input'"/>
      <Overview v-else/>
    </div>
  </div>
</template>

<script>
import Input from "./components/Input.vue";
import Overview from "./components/Overview.vue";
import "bootstrap";

export default {
  name: "app",
  data: function() {
    return {
      page: "Input"
    };
  },
  components: {
    Input,
    Overview
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