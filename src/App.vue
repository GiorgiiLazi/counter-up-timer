<template>
  <h1>George's Reaction Timer</h1>
  <button @click="countdown" class="start">
    Start countdown
  </button>
  <Block @stop="stopCountdown" v-if="start"></Block>
  <Results :timeElapsed="timerResult" v-if="showResult"></Results>
</template>

<script>

import Block from "./components/Block.vue"
import Results from "./components/Results.vue"
export default {
  name: 'App',
  components: {
    Block, Results
  },
  data(){
    return{
      start: false,
      showResult: false,
      timerResult: 0,
    }
  },
  methods: {
    countdown(){
      this.showResult = false
      setTimeout(()=>{
        this.start = true
      }, 4000)

    },
    stopCountdown(time){
      this.start = false;
      this.showResult = true;
      this.timerResult = time
    }
  }

  
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.start{
  border: none;
  background-color: hsl(120, 58%, 36%);
  margin: 50px 0px;
  padding: 20px 10px;
  border-radius: 8px;
  color: white;
  font-size: 15px;
  cursor: pointer;
}
</style>
