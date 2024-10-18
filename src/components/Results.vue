<template>
    <div class="results">
        <h2>Your score is {{ timeElapsed }}ms...</h2>
        <br>
        <h1>You are slow</h1>
  </div>
</template>

<script>
    export default{
        data(){
            return{
                score: null,
                result: [
                    {description: 'Turtles pace....'},
                    {description: 'You are slow....'},
                    {description: 'You are getting better....'},
                    {description: '....Fast as chetaah!!!'},
                ]
            }
        },
        props: ['timeElapsed']
        
    }
</script>

<style scoped>
    .results{
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
    }
    .results h2{
        color: crimson;
        text-decoration: underline;
    }
    .result h1{
        text-transform: uppercase;
    }

</style>