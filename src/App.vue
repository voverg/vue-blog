<template>
  <main class="App">
    <PostForm
      @create="createPost"
    />
    <PostList
      :posts="posts"
      @remove="removePost"
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
      removePost(post) {
        this.posts = this.posts.filter((p) => {
          return p.id !== post.id;
        });
      }
    }
  }
</script>

<style>
  :root {
    --blue: #1793b1;
  }

  html, body, * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Verdana, sans-serif;
    font-size: 16px;
    color: #555;
  }

  .App {
    margin: 0 auto;
    padding: 20px;
  }
</style>
