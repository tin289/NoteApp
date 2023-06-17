<template>
  <div class="container">
    <home-page></home-page>
  </div>
</template>

<script>
import HomePage from './components/Main/HomePage.vue'

export default {
  name: 'App',
  components: {
    HomePage
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: "Jost", sans-serif;
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
}
</style>
