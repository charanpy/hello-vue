<template>
  <h2>{{name}}</h2>
  <p>{{about}}</p>
</template>

<script>
export default {
  props: {
    name: String,
    about: String
  }
}
</script>

<style scoped>
h2,p{
  font-style: italic;
}
</style>