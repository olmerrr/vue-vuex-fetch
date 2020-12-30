<template>
  <div class="post-form-wrapp">
    <form @submit.prevent="submitForm">
      <input type="text" placeholder="Title" v-model="title"/>
      <input type="text" placeholder="Body" v-model="body"/>
      <button>Add</button>
    </form>
  </div>
</template>
<script>
  import {mapMutations} from 'vuex';
export default {
  name: 'post-form',
  data() {
      return {
        title: '',
        body: ''
      }
    },
    methods: {
      ...mapMutations(['createPost']),
      submitForm () {
        this.createPost({
          title: this.title,
          body: this.body,
          id: Date.now()
        });
        //очистка инпутов
        this.title = '';
        this.body = '';
      },
    },
  };
</script>
<style scoped>
  .post-form-wrapp {
    padding: 20px;
  }
  button {
    border-radius: 4px;
    width: 70px;
    }
</style>