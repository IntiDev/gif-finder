<template>
  <div id="app">
    <img alt="Giphy logo" src="./assets/logo.png" class="App-logo" />
    <div class="Search-container">
      <input type="text" placeholder="Teclea algo..."  v-model="keyword" v-on:keyup.enter="handleClick"/>
      <button v-on:click="handleClick">Buscar</button>
    </div>
    <GifsGrid
      :keyword="filter"
      :arrayGifs="arrayGifs"
      :searching="searching"
    />
  </div>
</template>

<script>
import GifsGrid from "./components/GifsGrid.vue";

export default {
  name: "App",
  data() {
    return {
      keyword: null,
      filter: "",
      arrayGifs: [],
      searching: false,
    }
  },
  methods: {
    handleClick: function () {
      this.searching = false;
      let url = "http://api.giphy.com/v1/gifs/search?api_key=Fv0qVqTBwlIwSdGbVBtkReYJASvlVX3G&limit=5&q="+this.keyword;
      this.filter = this.keyword;
      fetch(url)
      .then((response) => response.json())
      .then((data) => {
        this.arrayGifs = data.data;
        this.searching = true;
        this.keyword = "";
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
