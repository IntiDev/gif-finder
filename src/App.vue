<template>
  <div id="app">
    <img alt="Giphy logo" src="./assets/logo.png" class="App-logo" />
    <div class="Search-container">
      <input />
      <button>Buscar</button>
    </div>
    <GifsGrid msg="Welcome IntiDev" />
  </div>
</template>

<script>
import GifsGrid from "./components/GifsGrid.vue";

export default {
  name: "App",
  components: {
    GifsGrid,
  },
};
</script>

<style>
body {
  background-color: #f8f8f9;
  display: grid;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #576177;
  text-align: center;
}

.App-logo {
  width: 150px;
  margin: 15px;
  justify-self: center;
}

input {
  min-width: 170px;
  height: 20px;
  padding: 5px 8px;
  margin: 0 10px;
  font-size: 1rem;
  font-weight: 400;
  border: 1px solid #ced4da;
  border-radius: 5px;
}

button {
  min-width: 100px;
  height: 35px;
  padding: 5px 16px;
  font-size: 1rem;
  font-weight: 400;
  text-align: center;
  vertical-align: middle;
  color: #fff;
  background-color: #0093FF;
  border-color: #0093ff;
  border: 1px solid transparent;
  box-sizing: border-box;
  border-radius: 5px;
  cursor: pointer;
}

button:hover {
  background-color: #0084E6;
}
</style>
