<template>
  <header>
    <h1>
      <img src="../assets/logo.png" alt="Logotipo Alura Tracker" />
    </h1>
    <button class="button" @click="swithTheme()">{{ buttonText }}</button>
  </header>
</template>

<script>
import { defineComponent } from 'vue';

  export default defineComponent({
    emit: ['switchTheme'],
    data() {
      return {
        darkMode: false
      }
    },
    computed: {
      buttonText () {
        if (this.darkMode) {
          return 'Desativar modo escuro';
        } else {
          return 'Ativar modo escuro';
        }
      }
    },
    methods: {
      swithTheme() {
        this.darkMode = !this.darkMode;
        this.$emit('switchTheme', this.darkMode);
      }
    }
  })

</script>

<style scoped>
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
  text-align: center;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
