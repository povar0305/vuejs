<template>

<post-item v-for="post in posts" :key="post.id"   :post="post" ></post-item>
</template>

<script>
import PostItem from "@/components/postItem";

export default {
  name: "post" ,
  components: {PostItem},
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