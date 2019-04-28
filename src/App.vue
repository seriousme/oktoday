<template>
  <span>
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
        <ul class="navbar-nav" data-toggle="collapse" data-target=".navbar-collapse.show">
          <li class="nav-item" v-bind:class="{ active: page == 'Overview' }">
            <span class="nav-link" href="#" v-on:click="page = 'Input'">Invoer</span>
          </li>
          <li class="nav-item" v-bind:class="{ active: page == 'Input' }">
            <span class="nav-link" href="#" v-on:click="page = 'Overview'">Overzicht</span>
          </li>
        </ul>
      </div>
    </nav>
    <main class="container" style="max-width: 800px">
      <component v-bind:is="page" v-bind:records="records" v-on:save="save($event)"></component>
    </main>
  </span>
</template>

<script>
import Input from "./components/Input.vue";
import Overview from "./components/Overview.vue";
import "bootstrap";

const data = {
  records: [],
  page: "Input"
};

function save(record) {
  const noDuplicate = item => item.date !== record.date;
  const compare = (a, b) => {
    if (a.date > b.date) return -1;
    if (a.date < b.date) return 1;
    return 0;
  };
  const newRecords = data.records.filter(noDuplicate);
  newRecords.push(record);
  newRecords.sort(compare);
  data.records = newRecords;
  localStorage.setItem("records", JSON.stringify(data.records));
}

function load() {
  if (localStorage.getItem("records")) {
    try {
      data.records = JSON.parse(localStorage.getItem("records"));
    } catch (e) {
      localStorage.removeItem("records");
    }
  }
}

export default {
  name: "app",
  data: function() {
    return data;
  },
  components: {
    Input,
    Overview
  },
  mounted: load,
  methods: {
    save
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
