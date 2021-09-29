<template>
  <form class="new-post" @submit.prevent="createPost">
    <h3 class="new-post__title">Creating a new post</h3>
    <MyInput
      v-model="post.title"
      type="text"
      placeholder="Title"
    />
    <MyInput
      class="new-post__body"
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
    width: 60vw;
    height: 50vh;
    display: flex;
    flex-direction: column;
  }

  .new-post__title {
    margin-bottom: 15px;
  }

  .add-post {
    align-self: flex-end;
  }
</style>


