<template>
  <h2>Vuex</h2>
  <div class="post"
    v-for="post in allPosts"
    :key="post.id"
   >
   <h2>{{post.title}}</h2>
   <p>{{post.body}}</p>
  </div>
</template>

<script>
import {mapGetters} from 'vuex';

export default {
  name: "App",
  computed: mapGetters(['allPosts']),
  async mounted() {
    this.$store.dispatch("fetchPosts")
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.post{
  margin: 0 auto;
  max-width: 400px;
  padding: 10px;
  box-shadow: 0 1px 1px;
}
</style>
