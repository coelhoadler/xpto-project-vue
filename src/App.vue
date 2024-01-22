<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideNav />
    </div>
    <div class="column is-three-quarter">
      <MyForm />
      <div class="list">
        <MyTask />
      </div>
    </div>
  </main>
</template>

<script>
import { defineComponent } from "vue";
import SideNav from "./components/SideNav.vue";
import MyForm from './components/MyForm.vue'
import MyTask from './components/MyTask.vue'

export default defineComponent({
  name: "App",
  components: {
    SideNav,
    MyForm,
    MyTask,
  },
});
</script>

<style></style>
