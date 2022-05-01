
<template>
  <div class="app">
    <post-form @create="createPost" />

    <post-list :posts="posts" />
  </div>
</template>

/* ************************************************** */

<script>
import PostForm from "./components/PostForm";
import PostList from "./components/PostList";

export default {
  components: {
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [
        { id: 1, title: "javascipt", body: "Описание поста" },
        { id: 2, title: "javascipt2", body: "Описание поста2" },
        { id: 3, title: "javascipt3", body: "Описание поста3" },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

/* ************************************************** */

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}
</style>