<template>
  <header class="header">
        <!--<img class="logo" alt="Urlking logo" src="../assets/urlking-logo1.png">
        <h1>Urlking</h1>-->
        <div class="github">
            <a class="githubLink" href="https://github.com/sommerfe/urlking">
                <div class="githubContainer">
                    <img class="githubImg" src="../assets/GitHub-Mark-64px.png" alt="Github">
                    <!--<span>Checkout the Github Repo</span>-->
                </div>
            </a>
        </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  components: {
  }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  margin-bottom: 20px;
  /*background: #76b5c5;*/
}

.logo {
    width: 2%;
}

.github {
    margin: 10px;
}

.githubContainer {
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.githubLink {
    text-decoration: none;
    color: #2c3e50;
}

.githubImg {
    width: 25px;
    margin-right: 3px;
}

.githubImg:hover {
    opacity: 0.5;
    transition: 0.2s;
}
</style>