<template>

  <div id="task2" class="task post">
    <h1>Задание 2</h1>
    <div class="task_body">
      <div class="row justify-content-between">
        <p class="desc">Тут есть уже посты, вы можете создать свои посты и они сохранятся в local store</p>
        <btn @click="showForm = !showForm">
          <svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2" viewBox="0 0 24 24"
               xmlns="http://www.w3.org/2000/svg">
            <path
                d="m11 11h-7.25c-.414 0-.75.336-.75.75s.336.75.75.75h7.25v7.25c0 .414.336.75.75.75s.75-.336.75-.75v-7.25h7.25c.414 0 .75-.336.75-.75s-.336-.75-.75-.75h-7.25v-7.25c0-.414-.336-.75-.75-.75s-.75.336-.75.75z"
                fill-rule="nonzero"/>
          </svg>
        </btn>

      </div>
      <div class="  post_row ">
        <form-add-post @createPost="addPost" :showForm="showForm" :title="title"
                       :body="body"></form-add-post>
        <post :posts="posts"></post>
      </div>

    </div>
  </div>
</template>
<script>
import FormAddPost from "@/components/formAddPost.vue";
import Post from "@/components/post.vue";
import Btn from "@/components/UI/btn.vue";

export default {
  components: {
    FormAddPost,
    Post,
    Btn
  },

  data() {
    return {
      posts:[],
      showForm: false,
      title: '',
      body: '',
    }
  },
  methods: {
    addPost(post) {
      this.posts.push(post)
      localStorage.setItem('array_posts', JSON.stringify(this.posts));
    }
  },

  mounted(){
    this.posts=JSON.parse(localStorage.getItem("array_posts"));
  }


}



</script>
<style>

</style>