<template>
  <h2>Vuex</h2>
  <div class="post"
    v-for="post in posts"
    :key="post.id"
   >
   <h2>{{post.title}}</h2>
   <p>{{post.body}}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      posts: [],
    };
  },
  components: {},
  async mounted() {
    const res = await fetch("https://jsonplaceholder.typicode.com/posts?_limit=3");
    const posts = await res.json();
    this.posts = posts;
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
