<template>
  <input required :value="modelValue" @input="updateInput" type="text" placeholder="Текст"/>

</template>

<script>
export default {
  name: "myInput",
  props:{
    modelValue:[String]
  },
  methods:{
    updateInput(event){
      this.$emit('update:modelValue',event.target.value)
    }
  }

}

</script>

<style lang="scss" scoped>
$font-family: 'Montserrat', sans-serif;
$darken: #404040;
$dark: #8C8C8C;
$middle: #A6A6A6;
$light: #D9D9D9;
$bgc: #F2F2F2;
$white: white;
input {
  width: inherit;
  margin-right: 10px;
  padding: 10px 10px;
  background-color: $dark;
  color: $white;
@media(max-width: 768px) {
  width: 100%;
  margin-right: 0;
  margin-bottom: 10px;
}}

input::placeholder {
   color: $darken;
 }
</style>