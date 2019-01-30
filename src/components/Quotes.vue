<template>
    <div class="container">
        <div class="row">
            <single-quote class="col-3 my-1" 
            v-for="(quote, index) in quotes" :key=index >
               <div class="single-quote-wrapper px-3 py-1" @click="deleteQuote(index)">{{ quote }}</div> 
            </single-quote>
        </div>
    </div>
</template>
<script>
 import SingleQuote from './SingleQuote.vue'
 
export default {
    props:['quotes'],
    methods: {
        deleteQuote: function(index) {
            this.$emit('index', index)
        }
    },
    components: {
        'single-quote': SingleQuote
    }
}
</script>
<style scoped>
      .single-quote-wrapper{
        border: 2px solid black;
        border-radius: 10px;
      }
</style>
