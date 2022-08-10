<template>
  <div id="app">
    <Task1 :likes="likes" :dislikes="dislikes" ></Task1>
    <Task2 :posts="posts" :showForm="showForm"></Task2>
  </div>


</template>
<script>
import Task1 from "@/components/task1.vue";
import Task2 from "@/components/task2.vue";
export default {
  components:{
    Task1,
    Task2
  },
  data() {
    return {
      likes: 0,
      dislikes: 0,
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
  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    },
    sendForm() {
      let newPost = {
        id: String(Date.now()), title: this.titleForm, body: this.bodyForm
      }
      this.posts.push(newPost)
    this.titleForm=''
      this.bodyForm=''
    }

  }
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@100;300;500&display=swap');

$font-family: 'Montserrat', sans-serif;
$darken: #404040;
$dark: #8C8C8C;
$middle: #A6A6A6;
$light: #D9D9D9;
$bgc: #F2F2F2;
$white: white;
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: $font-family;
  border-radius: 0.25rem;
  transition: 0.3s;
}

body {
  background-color: $bgc;
}

h1 {
  font-size: 3rem;
  font-weight: 100;
  padding-bottom: 15px;
}

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}

.justify-content-between {
  justify-content: space-between !important;
}

svg {
  width: 24px;
  height: 24px;
}

.task {
  padding: 3rem;
  font-weight: 300;
  background-color: $light;
  margin-top: 1rem;
  margin-bottom: 1rem;

  & .desc {
    padding-bottom: 10px;
  }

  &_body {
    background-color: $middle;
    padding: 1rem;

    &-inner {
      background-color: $dark;
      padding: 1rem;

    }
  }

  & button {
    background-color: $darken;
    margin-right: 0.5rem;
    outline: none;
    color: $white;
    padding: 7px 20px;
  }

  & button path {
    fill: $white;
  }
}

.post {
  &_row {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: space-between;

    & form {
      width: 100%;
      display: flex;
      margin: 10px;
      justify-content: space-between;
      @media(max-width: 768px) {
        flex-direction: column;
      }

      & button {
        @media(max-width: 768px) {
          width: 100%;
          margin-right: 0;
          margin-bottom: 10px;
        }
      }

      & input {
        width: inherit;
        margin-right: 10px;
        padding: 10px 10px;
        background-color: $dark;
        color: $white;
        @media(max-width: 768px) {
          width: 100%;
          margin-right: 0;
          margin-bottom: 10px;
        }

        &::placeholder {
          color: $darken;
        }
      }

    }
  }

  &_card {
    display: flex;
    flex-direction: column;
    width: calc(50% - 20px);
    margin: 10px;
    @media(max-width: 768px) {
      width: 100%;
    }
    & p{
      text-align: justify;
    }
  }
}

button {
  border: 2px solid transparent;
}

button:hover {
  cursor: pointer;
  background-color: transparent;
  border: 2px solid $darken;
}

</style>