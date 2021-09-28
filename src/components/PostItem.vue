<template>
  <div class="post">
    <div class="post__content">
      <div class="post__title"><strong>Title: </strong>{{ post.title }}</div>
      <div class="post__body"><strong>Body: </strong>{{ post.body }}</div>
    </div>
    <div class="post__btns">
      <Btn
        @click="deletePost"
      >Delete</Btn>
    </div>

  </div>
</template>

<script>
  export default {
    props: {
      post: {
        type: Object,
        required: true
      }
    },
    methods: {
      deletePost() {
        this.$emit('remove', this.post);
      }
    }
  }
</script>

<style scoped>
  .post {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 15px;
    padding: 10px;
    border: 2px solid var(--blue);
    border-radius: 3px;
  }
</style>
