<template>
  <section class="Grid-container">
    <p v-if="msg !== ''">Resultados para {{ msg }}</p>
    <div class="Grid-items-container">
      <div class="Grid-item">
        <img
        src="https://media2.giphy.com/media/S9RUTgRxiFVEpOQ4jW/giphy.gif?cid=ddf33540fp5qn5nx2ms5msu5rvin8iv9y2678c8armq5w8mh&rid=giphy.gif"
      />
      </div>

      <div class="Grid-item">
        <img
        src="https://media2.giphy.com/media/S9RUTgRxiFVEpOQ4jW/giphy.gif?cid=ddf33540fp5qn5nx2ms5msu5rvin8iv9y2678c8armq5w8mh&rid=giphy.gif"
      />
      </div>

      <div class="Grid-item">
        <img
        src="https://media2.giphy.com/media/S9RUTgRxiFVEpOQ4jW/giphy.gif?cid=ddf33540fp5qn5nx2ms5msu5rvin8iv9y2678c8armq5w8mh&rid=giphy.gif"
      />
      </div>

      <div class="Grid-item">
        <img
        src="https://media2.giphy.com/media/S9RUTgRxiFVEpOQ4jW/giphy.gif?cid=ddf33540fp5qn5nx2ms5msu5rvin8iv9y2678c8armq5w8mh&rid=giphy.gif"
      />
      </div>

      <div class="Grid-item">
        <img
        src="https://media2.giphy.com/media/S9RUTgRxiFVEpOQ4jW/giphy.gif?cid=ddf33540fp5qn5nx2ms5msu5rvin8iv9y2678c8armq5w8mh&rid=giphy.gif"
      />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "GifsGrid",
  props: {
    msg: String,
    arrayGifs: Array,
  },
};
</script>

<style scoped>
p {
  font-size: 1rem;
}

.Grid-items-container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  margin-top: 20px;
  padding: 0 10px;
}

.Grid-item {
  padding: 5px;
}

img {
  max-width: 100%;
}


@media (max-width: 992px) {
  .Grid-items-container {
    grid-template-columns: repeat(4, 1fr);
  }
}

@media (max-width: 768px) {
  .Grid-items-container {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 480px) {
  .Grid-items-container {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
