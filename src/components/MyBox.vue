<template>
  <div class="box has-text-weight-bold">
    <slot></slot>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "MyBox",
});
</script>

<style scoped>
.box {
  background-color: #faf0ca;
}
</style>
