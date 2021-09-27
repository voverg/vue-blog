<template>
  <main class="main">
    <form class="new-post" @submit.prevent="createPost">
      <input
        @input="title = $event.target.value"
        v-bind:value="title"
        type="text"
        class="new-post__input"
        placeholder="Title"
      >
      <input
        @input="body = $event.target.value"
        v-bind:value="body"
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

    <div class="post" v-for="post in posts">
      <div class="post__title"><strong>Title: </strong>{{ post.title }}</div>
      <div class="post__body"><strong>Body: </strong>{{ post.body }}</div>
    </div>
  </main>
</template>

<script>
  export default {
    data() {
      return {
        posts: [
          {id: 1, title: 'Javascript', body: 'This is a post about Javascript'},
          {id: 2, title: 'Python', body: 'This is a post about Python'},
          {id: 3, title: 'Ruby', body: 'This is a post about Ruby'},
        ],
        title: '',
        body: ''
      }
    },
    methods: {
      createPost() {
        const newPost = {
          id: Date.now(),
          title: this.title,
          body: this.body
        };

        this.posts.push(newPost);
        this.title = '';
        this.body = '';
      },
    }
  }
</script>

<style>
  :root {
    --green: #1fe41f;
  }

  .main {
    margin: 0 auto;
    padding: 0 20px;
  }

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

  .post {
    margin-bottom: 15px;
    padding: 10px;
    border: 2px solid var(--green);
    border-radius: 3px;
  }
</style>
