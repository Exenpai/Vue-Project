<template>
  <div id="app">
    <Header></Header>
    <router-view />
  </div>
</template>

<script>
// @ is an alias to /src
import Header from "@/components/Header.vue";

export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

header {
  text-align: center;
  background-color: cornsilk;
  border: solid;
  width: max-content;
  margin: auto;
}

h1 {
  padding: 5px;
}

tr,
td {
  padding: 10px;
}

legend,
table {
  margin: auto;
}

.center {
  text-align: center;
  margin: auto;
}

.fixed {
  width: min-content;
}

.spacing {
  text-align: center;
  padding: 50px;
}

img:hover {
  /*increase img x2.67*/
  width: 200px;
  height: 200px;
  transition-duration: 1s;
}
</style>
