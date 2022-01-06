<template>
    <div class="main_container">
        <img alt="Vue logo" src="../assets/logo.png">
        <h1>Urlking</h1>
        <p>Explanation</p>
        <div class="">
            <Linker deviceName="Android" ph="Android Link" />
        </div>
    </div>

<!--    <input type="text" placeholder="Android link">
    <input type="text" placeholder="Apple link">
    <input type="text" placeholder="Desktop link">
    <button>Generate</button>
    <span>Generated Link</span>-->
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

</style>