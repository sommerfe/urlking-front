<template>
  <Header/>
  <div class="app-container">
    <Main class="main" />
  </div>
  <Footer/>
</template>

<script>
import Main from './components/Main.vue'
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer
  }
}
</script>

<style>
 @import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;500;600;700;800;900&display=swap');

*{
  margin: 0;
  padding: 0;
}
.main {
  grid-area: main;
}
.app-container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-areas: ". main .";
}

#app {
  font-family: Raleway, Dongle, Avenir, Helvetica, Arial, sans-serif;
  font-weight: 500;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

