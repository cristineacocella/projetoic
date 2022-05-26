<template>
  <Header />
  <Box />
</template>

<script>
import Header from "./components/Header.vue";
import Box from "./components/Box.vue";

export default {
  name: "App",
  components: {
    Header,
    Box,
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
