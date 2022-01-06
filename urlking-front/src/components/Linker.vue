<template>
    <div>
        <span>{{ deviceName }}</span>
        <input type="text" :placeholder="[[ph]]">
    </div>
</template>

<script>
    export default {
       name: 'Linker',
       props: {
           deviceName: String,
           ph: String
       }
    }
</script>

<style>

</style>