<template>
  <div class="app-container">
    <Header class="header"/>
    <Main class="main" />
    <Footer class="footer"/>
  </div>
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

.header {
  grid-area: header;
}

.footer {
  grid-area: footer;
}

.app-container {
  display: grid;
  grid-template-columns: [left] 1fr  [main] 2fr  [right] 1fr;
  grid-template-rows: auto 1fr auto;
  grid-template-areas: 
    "header header header"
    ". main ."
    "footer footer footer";
  min-height: 100%;
  /*grid-template-areas: ". main .";
  grid-template-rows: "header" "main" "footer";*/
}

#app {
  font-family: Raleway, Dongle, Avenir, Helvetica, Arial, sans-serif;
  font-weight: 500;
  height: 100vh;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>

