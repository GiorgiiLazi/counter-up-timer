<template>
  <div class="box" @click="finishCountdown">
    <div class="counter"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startTime: Date.now(),
      endTime: 0,
      timeElapsed: 0,
    };
  },
  methods: {
    finishCountdown() {
      this.endTime = Date.now();
      this.timeElapsed = this.endTime - this.startTime;
      this.startTime = Date.now();
      console.log(this.timeElapsed);
      this.$emit("stop", this.timeElapsed);
    },
    getTime() {
      // Get current Time
      this.startTime = Date.now();
    },
  },
};
</script>

<style scoped>
.box{
    margin: 0 auto;
    height: 300px;
    border: none;
    width: 500px;
    color: crimson;
    background-color: lightgreen;
    cursor: pointer;
}
</style>
