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
  export default {
    data() {
      return {
        inputTitle: '',
        inputBody: ''
      }
    },
    methods: {
      submitForm () {

      },
    }
  };
</script>
<style scoped>
  .post-form-wrapp {
    padding: 20px;
  }
</style>