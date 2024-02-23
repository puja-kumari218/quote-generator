<template>
  <div class="button-container">
    <base-button id="newQuote" @click="emitNewQuoteBtn">New Quote</base-button>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  emits: ["new-quote-btn"],
  methods: {
    emitNewQuoteBtn() {
      this.$emit("new-quote-btn");
    },
  },
});
</script>

<style scoped>
.button-container {
  margin-top: 15px;
  display: flex;
  justify-content: flex-end;
}
</style>
