<template>
  <div class=" post_card task_body-inner" v-for="post in posts" :key="post.id">
    <h2>{{ post.title }}</h2>
    <p>{{ post.body }}</p>

  </div>
</template>

<script>
export default {
  name: "post"
  ,
  props: {
    posts:{
      type:Array,
      required:true
    }
  }
}
</script>

<style scoped>

</style>