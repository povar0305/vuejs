<template>
  <div class=" post_card task_body-inner">

  <h2>{{ post.title }}</h2>
  <p>{{ post.body }}</p>
  </div>
</template>

<script>
export default {
  name: "postItem",
  props:{
    post:{
      type:Object,
      required:true,
    }
  }
}
</script>

<style scoped>

</style>