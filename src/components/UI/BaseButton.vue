<template>
  <button><slot></slot></button>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "BaseButton",
});
</script>

<style scoped>
button {
  cursor: pointer;
  font-size: 1.2rem;
  height: 2.5rem;
  border: none;
  border-radius: 10px;
  color: #fff;
  background: #333;
  outline: none;
  padding: 0.5rem 1.8rem;
  box-shadow: 0 0.3rem rgba(121, 121, 121, 0.65);
}
button:hover {
  filter: brightness(110%);
}
button:active {
  transform: translate(0, 0.3rem);
  box-shadow: 0 0.1rem rgba(255, 255, 255, 0.65);
}
</style>
