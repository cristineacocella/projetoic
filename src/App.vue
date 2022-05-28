<template>
  <HeaderNav />
  <BoxContent />
</template>

<script>
import HeaderNav from "./components/HeaderNav.vue";
import BoxContent from "./components/BoxContent.vue";

export default {
  name: "App",
  components: {
    HeaderNav,
    BoxContent,
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
