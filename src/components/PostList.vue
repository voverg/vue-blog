<template>
  <div class="post" v-for="post in posts">
    <div class="post__title"><strong>Title: </strong>{{ post.title }}</div>
    <div class="post__body"><strong>Body: </strong>{{ post.body }}</div>
  </div>
</template>

<script>
  export default {
    props: {
      posts: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>
  .post {
    margin-bottom: 15px;
    padding: 10px;
    border: 2px solid var(--green);
    border-radius: 3px;
  }
</style>
