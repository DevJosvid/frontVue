<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <Dropdown/>
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Dropdown from './components/dropdownFruits.vue'
// import 'materialize-css'
// import 'materialize-css/dist/css/materialize.css'
// import 'material-design-icons/iconfont/material-icons.css'
export default {
  name: 'App',
  components: {
    // HelloWorld,
    Dropdown
  }
}
</script>

<style>
body{
  background: #A0AEC0;
}
#app {
  /* background: #A0AEC0; */
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
  text-align: center;
  /* color: #2c3e50;
  margin-top: 60px; */
}
</style>
