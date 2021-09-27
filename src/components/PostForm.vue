<template>
  <form class="new-post" @submit.prevent="createPost">
    <input
      v-model="post.title"
      type="text"
      class="new-post__input"
      placeholder="Title"
    >
    <input
      v-model="post.body"
      type="text"
      class="new-post__input"
      placeholder="Description"
    >
    <button
      class="add-post"
    >
      Add post
    </button>
  </form>
</template>

<script>
  export default {
    data() {
      return {
        post: {
          title: '',
          body: ''
        }
      }
    },
    methods: {
      createPost() {
        this.post.id = Date.now();
        this.$emit('create', this.post);
        this.post = {
          title: '',
          body: ''
        }
      }
    }
  }
</script>

<style scoped>
  form.new-post {
    display: flex;
    flex-direction: column;
    margin-bottom: 15px;
    border-bottom: 1px solid var(--green);
  }

  .new-post__input {
    min-width: 97%;
    max-width: 100%;
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid var(--green);
    border-radius: 3px;
  }

  button.add-post {
    align-self: flex-end;
    margin-bottom: 10px;
    padding: 10px;
    background-color: var(--green);
    border: none;
    border-radius: 3px;
    color: #fff;
    cursor: pointer;
    transition: opacity .2s ease-out;
  }
  button.add-post:hover {
    opacity: 0.7;
  }
</style>


