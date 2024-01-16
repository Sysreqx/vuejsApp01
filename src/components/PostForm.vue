<template>
  <form @submit.prevent>
    <h4>Создание поста</h4>
    <input v-model="post.title" type="text" class="input" placeholder="Название">
    <input v-model="post.body" type="text" class="input" placeholder="Описание">
    <button class="btn" @click="createPost" >Создать</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      // Создать событие, отправить в родителя. чтобы с родителя можно было подписаться
      this.$emit("create", this.post, "second param", "3rd param")
      this.post = {
        title: "",
        body: ""
      }
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
    flex-direction: column;
  }

  .input {
    width: 100%;
    border: 1px solid teal;
    padding: 10px 15px;
    margin-top: 15px;
  }

  .btn {
    margin-top: 15px;
    align-self: flex-end;
    padding: 10px 15px;
    background: none;
    color: teal;
    border: 1px solid teal;
  }
</style>