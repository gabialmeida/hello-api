<template>
<div></div>
  <!--<img alt="Vue logo" src="./assets/logo.png">-->
  <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
  <HelloAPI />
</template>

<script>
// import HelloWorld from './components/HelloAPI.vue'
import HelloAPI from './components/HelloAPI.vue'

export default {
  name: 'App',
  components: {
    HelloAPI
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
