<template>
  <div class="Grid-container">
    <p v-if="msg !== ''"> Resultados para {{ msg }}</p>
  </div>
</template>

<script>
export default {
  name: 'GifsGrid',
  props: {
    msg: String,
    arrayGifs: Array
  }
}
</script>

<style scoped>
p {
  font-size: 1rem;
}
</style>
