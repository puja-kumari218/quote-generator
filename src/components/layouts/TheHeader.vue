<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  props: ["title"],
  setup(props) {
    const title = ref(props.title);
    return {
      title,
    };
  },
});
</script>

<style scoped>
header {
  width: 100%;
  height: 5rem;
  background-color: #0f0f0f;
  display: flex;
  justify-content: center;
  align-items: center;
}
header h1 {
  color: white;
  margin: 0;
}
</style>
