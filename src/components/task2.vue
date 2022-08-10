<template>

  <div id="task22" class="task post">
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
        <form v-if="showForm" @submit.prevent>
          <input v-bind:value='titleForm' @input="titleForm=$event.target.value" type="text"
                 placeholder="Название поста" required>
          <input v-bind:value='bodyForm' @input="bodyForm=$event.target.value" type="text" placeholder="Текст" required>
          <button @click="sendForm">Добавить пост</button>
        </form>
        <div class=" post_card task_body-inner" v-for="post in posts" :key="post.id">
          <h2>{{ post.title }}</h2>
          <p>{{ post.body }}</p>

        </div>
      </div>

    </div>
  </div>
</template>
<script>
export default {
  props:{
    posts:{
      type:Array,


}
  }
}
</script>
<style>

</style>