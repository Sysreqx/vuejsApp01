<script>
  import PostForm from "@/components/PostForm.vue";
  import PostList from "./components/PostList.vue";

  export default {
    components: {
      PostList,
      PostForm,
    },
    data() {
      return {
        posts: [
          {id: 1, title: "JavaScript 1", body: "Описание поста 1"},
          {id: 2, title: "JavaScript 2", body: "Описание поста 2"},
          {id: 3, title: "JavaScript 3", body: "Описание поста 3"},
        ],
      }
    },
    methods: {
      createPost(post) {
        this.posts.push(post);
      },

      // inputTitle(event) {
      //   this.title = event.target.value;
      // }
    }
  }
</script>

<template>
  <div class="app">
    <post-form @create="createPost"></post-form>
    <post-list :posts="posts"></post-list>
  </div>
</template>

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