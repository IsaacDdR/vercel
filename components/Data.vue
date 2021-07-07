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
  async asyncData({ $http }) {
    const artists = await $http.$get("https://lavoz.herokuapp.com/artistas");
    return { artists };
  },
  data() {
    return {
      artists: {}
    };
  },
  mounted() {
    console.log(artists);
  }
};
</script>
