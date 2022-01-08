<template>
    <div class="main-container">
        <img class="logo" alt="Urlking logo" src="../assets/urlking-logo1.png">
        <h1>Urlking</h1>
        <p>Explanation</p>
        <div class="">
            <Linker @inputChange="androidInput" deviceName="Android" ph="Android Link" />
            <Linker @inputChange="iosInput" deviceName="iOS" ph="iOS Link" />
            <Linker @inputChange="otherInput" deviceName="Other" ph="Other Link" />
        </div>
        <div class="generate-container">
            <button class="generate-button" v-on:click="generateLink">Generate</button>
            <span>{{ generatedLink }}</span>
        </div>
    </div>



</template>

<script>
import Linker from './Linker.vue'

export default {
    components: { Linker },
    name: 'Main',
    data() {
       return { androidLink: '',
        iosLink: '',
        otherLink: '',
        generatedLink: ''
       }
    },
   methods: {
       androidInput(link) {
           this.androidLink = link
           console.log(link)
       },

       iosInput(link) {
           this.iosLink = link
       },

       otherInput(link) {
           this.otherLink = link
       },

       generateLink () {
            console.log(this.androidLink)
            console.log(this.iosLink)
            console.log(this.otherLink)
            this.requestLink()
       },

       requestLink () {
            const requestOptions = {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: JSON.stringify({ 
                    windowsUrl: this.otherLink,
                    appleUrl: this.iosLink,
                    androidUrl: this.androidLink,
                    elseUrl: this.otherLink,
                    })
            };
            //fetch("http://localhost:8080/link", requestOptions)
            fetch("https://urlk.herokuapp.com/link", requestOptions)
                .then(response => response.json())
                .then(data => {
                    console.log(data)
                    this.generatedLink = data.returnUrl
                    //window.prompt("Copy to clipboard: Ctrl+C, Enter", this.generatedLink);
                });
        }
        
    }
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