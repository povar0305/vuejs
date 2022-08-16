<template>
  <form v-if="showForm" @submit.prevent>
    <input v-model='post.title'  required type="text" placeholder="Название поста">
    <input v-model='post.body' required  type="text" placeholder="Текст">
    <btn @click="sendForm">Добавить пост</btn>
  </form>
</template>

<script>
export default {
  name: "formAddPost",
  props: {
    showForm: {
      type: Boolean,
    },
    title: String,
    body: String,

  },
  data() {
    return {
      post: {
        title: '',
        body: '',
      }
    }
  },
  methods: {

    sendForm() {
      this.post.id = String(Date.now())
      this.$emit('createPost', this.post)
      this.post = {
        title: '',
        body: ''
      }

    }
  }
}
</script>

<style scoped>

</style>