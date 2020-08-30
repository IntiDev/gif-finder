<template>
  <div class="Grid-container">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'GifsGrid',
  props: {
    msg: String
  }
}
</script>

<style scoped>
h1 {
  color: #576177;
}
</style>
