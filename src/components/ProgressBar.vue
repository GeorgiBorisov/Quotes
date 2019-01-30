<template>
    <div class="container">
        <div class="progress progress-wrapper">
            <div class="progress-bar" :style="{'width': length  + '%'}" role="progressbar" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
                <span class="center">{{length}} %</span>
            </div>
        </div>
    </div>
</template>
<script>

export default {
    props: ['length']
   
}
</script>
<style scoped>
    .progress-wrapper{
        margin: 50px 0;
        font-size: 0.8rem;
        font-family: Arial, Helvetica, sans-serif;
    }
</style>
