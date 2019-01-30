<template>

    <div class="container">
        <progress-bar  :length="quotes.length"></progress-bar>
        <user-entry  :length="quotes.length" @new-quote="addQuote"></user-entry>
        <quotes :quotes="quotes" @index="removeQuote"></quotes>
        <status-message></status-message>
    </div>
</template>

<script>
    import Quotes from './components/Quotes.vue'
    import ProgressBar from './components/ProgressBar.vue'
    import UserEntry from './components/UserEntry.vue'
    import StatusMessage from './components/StatusMessage.vue'

    export default {
        data(){
            return{
                quotes: [
                    'Success is most often achieved by those who don\'t know that failure is inevitable.',
                    'Things work out best for those who make the best of how things work out.',
                    'Courage is grace under pressure.',
                    'If you are not willing to risk the usual, you will have to settle for the ordinary.'
                ]
            }
        },
        methods: {
            addQuote: function(e){
                if(e.length > 0 ){
                    this.quotes.push(e)
                }
            },
            removeQuote: function (e) {
                this.quotes.splice(e, 1)
            }
        },
        components:{
            'quotes': Quotes,
            'progress-bar': ProgressBar,
            'user-entry': UserEntry,
            'status-message': StatusMessage
        }
    }
</script>

<style>
    @font-face {
        font-family: 'Arizonia';
        src: "https://fonts.googleapis.com/css?family=Arizonia"
    }
    body {
        font-family: 'Arizonia';
        font-size: 2rem
    }
</style>
