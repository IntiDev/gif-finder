<template>
  <div id="app">
    <img alt="Giphy logo" src="./assets/logo.png" class="App-logo" />
    <div class="Search-container">
      <input type="text" placeholder="Teclea algo..."  v-model="keyword" v-on:keyup.enter="handleClick"/>
      <button v-on:click="handleClick">Buscar</button>
    </div>
    <GifsGrid
      :msg="keyword"
      :arrayGifs="arrayGifs"
    />
  </div>
</template>

<script>
import Vue from 'vue';
import GifsGrid from "./components/GifsGrid.vue";

export default {
  name: "App",
  data() {
    return {
      keyword: '',
      arrayGifs: []
    }
  },
  methods: {
    handleClick: function () {
      let url = "http://api.giphy.com/v1/gifs/search?api_key=XW1HTpw6EWg9S4z8EYwbMoBy1lUOfc5o&limit=5&q="+this.keyword;
      fetch(url)
      .then((response) => response.json())
      .then((data) => {
        console.log(data.data);
        this.arrayGifs = data.data;
      })
      .catch((error) => console.error(error));
    }
  },
  components: {
    GifsGrid,
  },
};
</script>

<style>
body {
  background-color: #f8f8f9;
  margin: 0;
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
