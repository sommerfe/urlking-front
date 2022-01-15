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
     align-items: center;
 }

 input {
     width: 80%;
     padding: 5px;
     font: inherit;
     font-weight: 400;
     border-radius: 5px;
     border: 1px solid gray;
 }
</style>