<script>
import { defineComponent } from "vue";
import TheHeader from "./components/layouts/TheHeader.vue";
import QuoteGenerator from "./components/quote-generator/QuoteComponent/QuoteComponent.vue";

export default defineComponent({
  name: "App",
  components: {
    TheHeader,
    QuoteGenerator,
  },
});
</script>

<template>
  <transition name="fade" appear>
    <div>
      <TheHeader title="Welcome to Quote App" />
      <QuoteGenerator />
    </div>
  </transition>
</template>

<style scoped>
@import "./App.css";
</style>
