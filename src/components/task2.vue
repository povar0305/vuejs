<template>

  <div id="task2" class="task post">
    <h1>Задание 2</h1>
    <div class="task_body">
      <div class="row justify-content-between">
        <p class="desc">Тут есть уже посты, вы можете создать свои посты и они сохранятся в local store</p>
        <button @click="showForm = !showForm">
          <svg clip-rule="evenodd" fill-rule="evenodd" stroke-linejoin="round" stroke-miterlimit="2" viewBox="0 0 24 24"
               xmlns="http://www.w3.org/2000/svg">
            <path
                d="m11 11h-7.25c-.414 0-.75.336-.75.75s.336.75.75.75h7.25v7.25c0 .414.336.75.75.75s.75-.336.75-.75v-7.25h7.25c.414 0 .75-.336.75-.75s-.336-.75-.75-.75h-7.25v-7.25c0-.414-.336-.75-.75-.75s-.75.336-.75.75z"
                fill-rule="nonzero"/>
          </svg>
        </button>

      </div>
      <div class="  post_row ">
        <form-add-post :showForm="showForm" :titleForm="titleForm" :bodyForm="bodyForm"></form-add-post>
        <post  :posts="posts"></post>
      </div>

    </div>
  </div>
</template>
<script>
import FormAddPost from "@/components/formAddPost.vue";
import  Post from "@/components/post.vue";

export default {
  components: {
    FormAddPost,
    Post
  },

  data() {
    return {
      posts: [
        {
          id: '1',
          title: 'Меня зовут София Поварницина',
          body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid, blanditiis cum deserunt dolor doloremque explicabo facilis incidunt ipsam iste iusto molestiae provident qui quidem rem reprehenderit sunt totam voluptates, voluptatibus?'
        },
        {
          id: '2',
          title: 'Это отработка опыта с vue3',
          body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Amet cum debitis dignissimos eius eligendi illo llum magni obcaecati optio, quisquam saepe similique tempore! Fuga illum inventore, itaque odio saepe suscipit!'
        },
        {
          id: '3',
          title: 'Посты отрисовываются с помощью v-for из массива',
          body: 'Blanditiis consequatur corporis culpa, deleniti doloremque dolores error id inventore iure iusto labore natus   nihil optio quam qui reiciendis reprehenderit saepe ut! Dolore doloribus dolorum exercitationem, ipsa ipsam   molestiae tenetur?'
        },
        {
          id: '4',
          title: 'Последний пост',
          body: 'Accusamus adipisci assumenda commodi dicta dolorem, dolorum eligendi esse, illo in ipsa iste labore maiores  minima natus nobis nostrum odio optio pariatur perferendis possimus praesentium quam rerum sed unde voluptatem! '
        },

      ],
      showForm: false,
      titleForm: '',
      bodyForm: '',
    }
  },


}
</script>
<style>

</style>