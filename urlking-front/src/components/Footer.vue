<template>
  <footer>
        <div class="impressumHeader">
            Informations / Impressum
        </div>
        <div class="impressumContainer">
            <div class="openSource">
                Open Source Repositories:
                <a href="https://github.com/sommerfe/urlking-front">Frontend</a>
                <a href="https://github.com/sommerfe/urlking">Backend</a>
            </div>
            <div class="name">
                Felix Sommer
            </div>
            <div>
                10 Rue du Moulin, 92170 Vanves - France
            </div>
            <div>
                sommer.businessmail@gmail.com
            </div>
        </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  components: {
  }
}
</script>

<style scoped>

footer {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 5.4rem;
  background-color: lightgray;
  font-size: 0.7rem;
}

.impressumHeader {
    font-size: 0.8rem;
    font-weight: bold;
    margin: 5px 0px;
}

.openSource {
    display: flex;
    flex-direction: row;
    justify-content: center;
    gap: 10px;
}

a {
    text-decoration: none;
    color: #0C59AC;
    font-weight: bold;
}

.name {
   margin-top: 5px;
}

.impressumContainer {
}
</style>