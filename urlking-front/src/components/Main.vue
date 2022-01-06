<template>
    <div class="main-container">
        <img class="logo" alt="Urlking logo" src="../assets/urlking-logo1.png">
        <h1>Urlking</h1>
        <p>Explanation</p>
        <div class="">
            <Linker deviceName="Android" ph="Android Link" />
            <Linker deviceName="iOS" ph="iOS Link" />
            <Linker deviceName="Other" ph="Other Link" />
        </div>
        <div class="generate-container">
            <button class="generate-button">Generate</button>
            <span>Generated Link</span>
        </div>
    </div>



</template>

<script>
import Linker from './Linker.vue'

export default {
    components: { Linker },
    name: 'Main',
  //  data: () => ({
   //     deviceName: 'Android',
   //     ph: 'Android link'
   // })
}
</script>

<style>
.generate-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 10px 0px;
}

.generate-button {
    width: 50%;
}

.logo {
    width: 10%;
}
</style>