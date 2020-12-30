<template>
  <h2>Vuex</h2>
  <p>Количество постов: {{postsCount}}</p>
  <div class="post"
    v-for="post in allPosts"
    :key="post.id"
   >
   <h2>{{post.title}}</h2>
   <p>{{post.body}}</p>
  </div>
  <post-form></post-form>
</template>

<script>
import {mapGetters, mapActions} from 'vuex';
import PostForm from './components/PostForm.vue';

export default {
  name: "App",
  computed: mapGetters(['allPosts', 'postsCount']),
  methods: mapActions(['fetchPosts']),
  async mounted() {
    this.fetchPosts(4); //количество лимитированых постов
  },
  components: {
    PostForm
  }
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
