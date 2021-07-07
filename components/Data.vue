<template>
  <div>
    <h1>Artists</h1>
    <ul v-for="mountain in artists" :key="mountain.slug">
      <li>{{ mountain.nombre }}</li>
    </ul>
  </div>
</template>
<script>
export default {
  data() {
    return {
      artists: []
    };
  },
  async fetch() {
    this.artists = await this.$http.$get(
      "https://lavoz.herokuapp.com/artistas"
    );
  }
};
</script>
