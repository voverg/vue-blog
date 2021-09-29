<template>
  <main class="App">
    <header class="App__header">
      <h1 class="App__title">Post list</h1>
      <Btn
        class="show-modal"
        @click="showModal"
      >
        Add a new post
      </Btn>
    </header>

    <MyModal v-model:show="modalVisible">
      <PostForm
        @click.stop
        @create="createPost"
      />
    </MyModal>

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
        modalVisible: false
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post);
        this.modalVisible = false;
      },
      removePost(post) {
        this.posts = this.posts.filter((p) => {
          return p.id !== post.id;
        });
      },
      showModal() {
        this.modalVisible = true;
      }
    }
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,300;0,500;0,700;1,300;1,500;1,700&display=swap');
  :root {
    --blue: #1793b1;
  }

  html, body, * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Roboto, sans-serif;
    font-size: 16px;
    color: #555;
  }

  .App {
    margin: 0 auto;
    padding: 20px;
  }

  .App__header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
  }

  .App__title {
    font-size: 36px;
    text-align: center;
    margin-bottom: 30px;
  }

  .show-modal {
    width: 20%;
    height: 40px;
  }
</style>
