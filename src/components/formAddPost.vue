<template>
  <form v-if="showForm" @submit.prevent>
    <input v-bind:value='post.titleForm' @input="post.titleForm=$event.target.value" type="text"
           placeholder="Название поста" required>
    <input v-bind:value='post.bodyForm' @input="post.bodyForm=$event.target.value" type="text" placeholder="Текст" required>
    <button @click="sendForm">Добавить пост</button>
  </form>
</template>

<script>
export default {
  name: "formAddPost",
  props: {
    showForm: {
      type: Boolean,
    },
    titleForm: String,
    bodyForm: String,

  },
  data() {
    return {
      post: {
        titleForm: '',
        bodyForm: '',
      }
    }
  },
  methods: {

    sendForm() {
      let newPost = {
        id: String(Date.now()), title: this.titleForm, body: this.bodyForm
      }
      this.posts.push(newPost)
      this.titleForm = ''
      this.bodyForm = ''
    }

  }
}
</script>

<style scoped>

</style>