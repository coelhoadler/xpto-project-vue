<template>
  <section>
    <strong class="watch-text">{{ elapsedTime }}</strong>
  </section>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "StopWatch",
  props: {
    timeInSeconds: {
        type: Number,
        default: 0
    }
  },
  computed: {
    elapsedTime() {
      return new Date(this.timeInSeconds * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>

<style>
  .watch-text {
    color: var(--primary-text);
  }
</style>
