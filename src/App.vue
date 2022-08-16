<template>
  <div id="app">
    <Task1></Task1>
    <Task2></Task2>
  </div>


</template>
<script>
import Task1 from "@/components/task1.vue";
import Task2 from "@/components/task2.vue";

export default {
  components: {
    Task1,
    Task2
  },


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
  margin: 1rem;
  @media(max-width: 768px) {
    margin-left: 0;
    margin-right: 0;
    padding: 1rem;
  }

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

    & p {
      text-align: justify;
    }
  }
}


</style>