<script>
  import PostForm from "@/components/PostForm.vue";
  import PostList from "./components/PostList.vue";

  export default {
    data() {
      return {
        posts: [
          {id: 1, title: "JavaScript 1", body: "Описание поста 1"},
          {id: 2, title: "JavaScript 2", body: "Описание поста 2"},
          {id: 3, title: "JavaScript 3", body: "Описание поста 3"},
        ],
        title: "",
        body: "",
      }
    },
    methods: {
      createPost() {
        const newPost = {
          id: Date.now(),
          title: this.title,
          body: this.body,
        }

        this.posts.push(newPost);
        this.title = "";
        this.body = "";
      },

      // inputTitle(event) {
      //   this.title = event.target.value;
      // }
    }
  }
</script>

<template>
  <div class="app">



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