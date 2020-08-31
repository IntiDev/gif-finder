<template>
  <section class="Grid-container" v-if="arrayGifs.length > 0" >
    <div class="Grid-items-container">
      <div class="Grid-item" v-for="gif in arrayGifs" :key="gif.id">
        <img
          :src="gif.images.downsized_medium.url"
        />
      </div>
    </div>
  </section>
  <p v-else-if="searching === true && arrayGifs.length === 0" >
    No se encontraron resultados para <strong>{{ keyword }}</strong>
  </p>
</template>

<script>

export default {
  name: "GifsGrid",
  props: {
    keyword: String,
    arrayGifs: Array,
    searching: Boolean,
  },
};
</script>

<style scoped>
p {
  font-size: 1rem;
  margin-top: 25px;
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
