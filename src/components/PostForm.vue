<template>
  <div class="post-form-wrapp">
    <form @submit.prevent="submitForm">
      <input type="text" placeholder="Title" v-model="inputTitle"/>
      <input type="text" placeholder="Body" v-model="inputBody"/>
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
        inputTitle: '',
        inputBody: ''
      }
    },
    methods: {
      ...mapMutations(['createPost']),
      submitForm () {
        this.createPost({
          title: this.inputTitle,
          body: this.inputBody,
          id: Date.now()
        });
        //очистка инпутов
        this.inputTitle = '';
        this.inputBody = '';
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