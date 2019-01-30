<template>
    <div class="form-group">
        <form>
            <label for="textEntry">Enter new quote</label>
            <textarea class="form-control" id="textEntry" cols="30" rows="5" v-model="newQuote"></textarea>
            <button v-if="length < 100" type="button" class="btn btn-primary" @click="addQuote(newQuote)">Add new quote</button>
        </form>
         <div class="row">
             <div v-if="length >= 100" class="col-md-12 status-alert-wrapper text-center">
                <p>Alert: No more quotes can be added</p>
            </div>
         </div>
    </div>
   
</template>
<script>
export default {
     props: ['length'],
    data(){
        return {
            newQuote: '' 
        }
    },
    methods: {
        addQuote: function(newQuote){
            this.$emit('new-quote', this.newQuote)
            
        }
    }
}
</script>
<style scoped>
    .form-group{
        font-family: Arial, Helvetica, sans-serif
    }
    button{
        margin-top: 20px;
        font-size: 1rem;
    }
    textarea{
        resize: none;
         font-size: 1.5rem !important;
    }
    .status-alert-wrapper{
        padding: 20px;
        background: lightcoral;
        margin-top: 20px;
        border-radius: 15px;
        border:  2px solid rgb(224, 30, 30);
        color: #fff;
    }
</style>
