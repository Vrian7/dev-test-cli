<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Trello msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Trello from './components/Trello.vue'
window.axios = require('axios')
export default {
  name: 'App',
  components: {
   // HelloWorld,
    Trello,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
