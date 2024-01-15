<script>
  export default {
    data() {
      return {
        likes: 0,
        dislikes: 5,
      }
    },
    methods: {
      addLike() {
        this.likes += 1;
      },
      addDislike() {
        this.dislikes += 1;
      }
    }
  }
</script>

<template>
  <div>
    <div>Количество лайков <strong>{{ likes }}</strong></div>
    <div>Количество лайков <strong>{{ dislikes }}</strong></div>

    <br>

    <button @click="addLike">like</button>
    <button v-on:click="addDislike">dislike</button>
  </div>
</template>

<style scoped>

</style>