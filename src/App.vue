<template>
  <div id="app">
    <img alt="Giphy logo" src="./assets/logo.png" class="App-logo">
    <GifsGrid msg="Welcome IntiDev"/>
  </div>
</template>

<script>
import GifsGrid from './components/GifsGrid.vue'

export default {
  name: 'App',
  components: {
    GifsGrid
  }
}
</script>

<style>
body {
  background-color: #F8F8F9;
  display: grid;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}

.App-logo {
  width: 150px;
  margin: 15px;
  justify-self: center;
}
</style>
