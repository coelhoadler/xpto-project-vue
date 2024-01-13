<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideNav />
    </div>
    <div class="column is-three-quarter">ww</div>
  </main>
</template>

<script>
import { defineComponent } from "vue";
import SideNav from "./components/SideNav.vue";

export default defineComponent({
  name: "App",
  components: {
    SideNav,
  },
});
</script>

<style></style>
