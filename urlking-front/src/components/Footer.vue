<template>
  <footer>
        <div class="impressumHeader" v-on:click="toggleImpressum">
            Informations / Impressum
        </div>
        <div v-if="showImpressum">
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
  },
    data() {
        return {
        showImpressum: false
        }
    },
    methods: {
        toggleImpressum() {
            this.showImpressum = !this.showImpressum
        }
    }
}
</script>

<style scoped>

footer {
  background-color: lightgray;
  font-size: 0.7rem;
}

.impressumHeader {
    font-size: 0.8rem;
    font-weight: bold;
    margin: 5px 0px;
    cursor: pointer;
}

.impressumHeader:hover {
    text-decoration: underline;
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
    display: none;
}
</style>