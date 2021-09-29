<template>
  <div class="post-list" v-if="posts.length > 0">
    <PostItem
      v-for="post in posts"
      :post="post"
      :key="post.id"
      @remove="$emit('remove', post)"
    />
  </div>

  <h3 class="empty-list" v-else>Post list is empty.</h3>
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

  .empty-list {
    text-align: center;
    color: #555;
  }
</style>
