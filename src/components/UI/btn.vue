<template>
  <button>
<slot></slot>
  </button>
</template>

<script>
export default {
  name: "btn"
}
</script>

<style scoped lang="scss">
$font-family: 'Montserrat', sans-serif;
$darken: #404040;
$dark: #8C8C8C;
$middle: #A6A6A6;
$light: #D9D9D9;
$bgc: #F2F2F2;
$white: white;
button {
  background-color: $darken;
  margin-right: 0.5rem;
  outline: none;
  color: $white;
  padding: 7px 20px;
  border: 2px solid transparent;
}
button path {
  fill: $white;
}
button svg{
  width: 24px;
  height: 24px;
}


button:hover {
  cursor: pointer;
  background-color: transparent;
  border: 2px solid $darken;
}
</style>