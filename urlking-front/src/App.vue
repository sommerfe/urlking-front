<template>
  <div class="app_container">
    <Main class="main" />
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Main from './components/Main.vue'
export default {
  name: 'App',
  components: {
    //HelloWorld,
    Main
  }
}
</script>

<style>
.main {
  grid-area: main;
}
.app_container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-areas: ". main .";
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

