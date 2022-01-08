<template>
    <div class="linker-container">
        <span>{{ deviceName }}</span>
        <input type="text" :placeholder="[[ph]]" @change="changeHandler">
    </div>
</template>

<script>
    export default {
       name: 'Linker',
       props: {
           deviceName: String,
           ph: String
       },
       methods : {
           changeHandler(e) {
               this.$emit('inputChange', e.target.value)
           }
       }
    }
</script>

<style>
 /*.linker-container {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    margin: 10px 0px;
 }*/
 .linker-container {
     display: grid;
     grid-template-columns: 1fr 2fr;
     margin: 10px 0px;
 }

 input {
     width: 80%;
 }
</style>