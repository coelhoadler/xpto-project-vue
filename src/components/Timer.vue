<template>
  <StopWatch :timeInSeconds="timeInSeconds" />
  <button class="button" @click="iniciar()" :disabled="timerIsStarted">
    <span class="icon">
      <i class="fas fa-play"></i>
    </span>
    <span>play</span>
  </button>
  <button class="button" @click="finalizar()" :disabled="!timerIsStarted">
    <span class="icon">
      <i class="fas fa-stop"></i>
    </span>
    <span>stop</span>
  </button>
</template>

<script>
import { defineComponent } from "vue";
import StopWatch from "./StopWatch.vue";

export default defineComponent({
  name: "Timer",
  components: {
    StopWatch,
  },
  data() {
    return {
      timeInSeconds: 0,
      timer: 0,
      timerIsStarted: false,
    };
  },
  methods: {
    iniciar() {
      this.timerIsStarted = true;
      this.timer = setInterval(() => {
        this.timeInSeconds++;
      }, 1000);
    },
    finalizar() {
      this.timerIsStarted = false;
      clearInterval(this.timer);
      this.$emit('timerFinished', this.timeInSeconds);
      this.timeInSeconds = 0;
    },
  },
  emits: [
    'timerFinished'
  ]
});
</script>

<style scoped></style>
