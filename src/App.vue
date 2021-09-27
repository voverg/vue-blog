<template>
  <main class="App">
    <PostForm
      @create="createPost"
    />
    <PostList
      :posts="posts"

    />
  </main>
</template>

<script>
  import PostForm from '@/components/PostForm';
  import PostList from '@/components/PostList';

  export default {
    components: {
      PostList,
      PostForm
    },
    data() {
      return {
        posts: [
          {id: 1, title: 'Javascript', body: 'This is a post about Javascript'},
          {id: 2, title: 'Python', body: 'This is a post about Python'},
          {id: 3, title: 'Ruby', body: 'This is a post about Ruby'},
        ],
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post);
      },
    }
  }
</script>

<style>
  :root {
    --green: #1fe41f;
  }

  .App {
    margin: 0 auto;
    padding: 0 20px;
  }
</style>
