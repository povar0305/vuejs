<template>
  <form v-if="showForm" @submit.prevent>
    <input v-model='post.titleForm' type="text" placeholder="Название поста">
    <input v-model='post.bodyForm' type="text" placeholder="Текст">
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
      this.post.id = String(Date.now())
      this.$emit('createPost', this.post)
      this.post = {
        titleForm: '',
        bodyForm: ''
      }

    }
  }
}
</script>

<style scoped>

</style>