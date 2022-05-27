<template>
  <vue-csv-import v-model="csv">
    <Header />
    <Box />
  </vue-csv-import>
</template>

<script>
import Header from "./components/Header.vue";
import Box from "./components/Box.vue";
import { VueCsvImport } from "vue-csv-import";

export default {
  name: "App",
  components: {
    Header,
    Box,
    VueCsvImport,
  },
};
</script>

<style>
#app {
  font-family: Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  font-size: 62.5%;
}

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
