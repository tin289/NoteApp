<template>
  <div class="container">
    <log-in v-if="show" @startNote="Start" ></log-in>
    <home-page v-else @LogOut="Quit"></home-page>
  </div>
</template>

<script>
import HomePage from './components/Main/HomePage.vue'
import LogIn from './components/LogIn/LogIn.vue'

export default {
  name: 'App',
  components: {
    HomePage,
    LogIn
  },
  
  data() {
    return {
      show: true,
    }
  },

  methods: {
    Start() {
      this.show = false
    },
    Quit() {
     this.show = true
    }
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
