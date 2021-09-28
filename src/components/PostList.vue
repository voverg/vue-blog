<template>
  <div class="post-list">
    <h3 class="post-list__title">User list</h3>
    <PostItem
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>
</template>

<script>
  import PostItem from '@/components/PostItem';

  export default {
    components: {
      PostItem
    },
    props: {
      posts: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>
  .post-list__title {
    margin: 20px 0 10px;
    text-align: center;
  }
</style>
