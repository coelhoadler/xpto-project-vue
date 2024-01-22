<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova task"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="taskDescription"
        />
      </div>
      <div class="column is-4">
        <div
          class="is-flex is-align-items-center is-justify-content-space-between"
        >
          <Timer @timer-finished="submitTask" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import {  defineComponent } from 'vue';
import Timer from './Timer.vue';

export default defineComponent({
  data() {
    return {
      taskDescription: ''
    }
  },
  components: {
    Timer
  },
  methods: {
    submitTask(timeInSeconds) {
      console.log('terminando task', timeInSeconds);
      console.log('descricao da tarefa', this.taskDescription);
      this.taskDescription = '';
    }
  }
})
</script>


<style scoped></style>
