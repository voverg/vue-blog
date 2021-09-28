<template>
  <form class="new-post" @submit.prevent="createPost">
    <my-input
      v-model="post.title"
      type="text"
      placeholder="Title"
    />
    <my-input
      v-model="post.body"
      type="text"
      placeholder="Description"
    />
    <Btn
      class="add-post"
    >
      Add post
    </Btn>
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
    border-bottom: 1px solid var(--blue);
  }

  .add-post {
    align-self: flex-end;
    margin-bottom: 10px;
  }
</style>


