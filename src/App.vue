<template>
  <main class="columns is-gapless is-multiline content" :class="{ 'dark-theme': isDarkMode }">
    <div class="column is-one-quarter">
      <SideNav @switchTheme="changeTheme" />
    </div>
    <div class="column is-three-quarter">
      <MyForm @emitNewTask="saveNewTask" />
      <div class="list">
        <MyTask v-for="(task, index) in tasks" v-bind:key="index" :taskObj="task" />
        <MyBox v-if="tasks.length === 0">
          Nenhuma Tarefa até o momento.
        </MyBox>
      </div>
    </div>
  </main>
</template>

<script>
import { defineComponent } from "vue";
import SideNav from "./components/SideNav.vue";
import MyForm from "./components/MyForm.vue";
import MyTask from "./components/MyTask.vue";
import MyBox from "./components/MyBox.vue";

export default defineComponent({
  name: "App",
  components: {
    SideNav,
    MyForm,
    MyTask,
    MyBox
  },
  data() {
    return {
      tasks: [],
      isDarkMode: false
    };
  },
  methods: {
    saveNewTask(task) {
      this.tasks.push(task);
    },
    changeTheme(isDarkTheme) {
      console.log('mudandoooo', isDarkTheme)
      this.isDarkMode = isDarkTheme;
    }
  }
});
</script>

<style>
.list {
  padding: 1.25rem;
}

main {
  --primary-bg: #fff;
  --primary-text: #000;
}

main.dark-theme {
  --primary-bg: #2b2d42;
  --primary-text: #ddd;
}

.content {
  transition: all .3s ease-in-out;
  background-color: var(--primary-bg);
  color: var(--primary-text);
}

</style>
