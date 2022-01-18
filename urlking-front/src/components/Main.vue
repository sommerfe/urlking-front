<template>
    <div class="main-container">
        <img class="logo" alt="Urlking logo" src="../assets/urlking-logo1.png">
        <h1 class="title">Urlking</h1>
        <p>Insert URLs to create a redirect link automatically redirecting by device</p>
        <div class="linkContainer">
            <Linker @inputChange="otherInput" deviceName="Default" ph="Default Link" />
            <Linker @inputChange="androidInput" deviceName="Android" ph="Android Link" />
            <Linker @inputChange="iosInput" deviceName="iOS" ph="iOS Link" />
        </div>
        <div class="generate-container">
            <button class="generate-button" v-on:click="generateLink">Generate Redirect Link</button>
            <div v-if="generatedLink" class="generatedLinkContainer">
                <span v-if="generatedLink" class="generatedLink">{{ generatedLink }}</span>
            </div>
            <span v-if="error" class="generateError">{{ error }}</span>
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
        generatedLink: '',
        error: ''
       }
    },
    title: 'UrlKing',

   methods: {
       androidInput(link) {
           if (this.checkUrl(link)) {
                this.androidLink = link
                console.log(link)
                this.error = ''
           } else {
                this.error = 'Invalid URL'
           }
       },

       iosInput(link) {
            if (this.checkUrl(link)) {
                this.iosLink = link
                this.error = ''
            } else {
                this.error = 'Invalid URL'
           }
       },

       otherInput(link) {
            if (this.checkUrl(link)) {
                this.otherLink = link
                this.error = ''
            } else {
                this.error = 'Invalid URL'
           }
       },

       checkUrl (url) {
            var expression = /[-a-zA-Z0-9@:%._+~#=]{1,256}\.[a-zA-Z0-9()]{1,6}\b([-a-zA-Z0-9()@:%_+.~#?&//=]*)?/gi;
            var regex = new RegExp(expression);
            return url.match(regex);
       },

       generateLink () {
           if (this.androidLink || this.iosLink || this.otherLink) {
            console.log(this.androidLink)
            console.log(this.iosLink)
            console.log(this.otherLink)
            this.error = ''
            this.requestLink()
           } else {
               this.error = 'Please enter a valid link'
           }
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
            //fetch("http://localhost:8080/link", requestOptions) https://urlk.herokuapp.com/link/61e29af325bb90f8a67c4d86
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
    margin: 20px 0px;
    gap: 10px;
    align-items: center;
}

p {
    padding-bottom: 15px;
    border-bottom: 1.5px solid #E0E0E0;
}

.linkContainer {
    margin-top: 20px;
}

.generate-button {
    width: 50%;
    padding: 5px;
    font: inherit;
    font-size: 1.2em;
    background-color: #0C59AC;
    color: white;
    border: none;
    font-weight: 700;
}

.generate-button:hover {
    cursor: pointer;
    background-color: #083D77;
    border-radius: 5px;
    transition: 0.3s;
}

.logo {
    width: 10%;
}

.generatedLink{
    margin: 10px 0px;
    padding: 5px 20px;
}

.generateError {
    background-color: #E78888;
    border-radius: 5px;
    padding: 5px 10px;
}

.generatedLinkContainer {
    padding: 10px;
    border-radius: 5px;
    background-color: #96CC8E;
}

.title {
    margin-bottom: 15px;
    margin-top: 5px;
}
</style>