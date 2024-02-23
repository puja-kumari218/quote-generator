<template>
  <div class="quote-container" id="quote-container">
    <div class="quote-text">
      <i class="fas fa-quote-left"></i>
      <span id="quote" :class="addLongQuoteClass">{{ quote }}</span>
    </div>
    <div class="quote-author">
      <span id="author">{{ quoteAuthor }}</span>
    </div>
    <ButtonContainer @new-quote-btn="getQuote"/>
  </div>
</template>

<script setup>
import { ref } from "vue";
import ButtonContainer from "../ButtonContainer/ButtonContainer.vue";

const quote = ref("");
const quoteAuthor = ref("");
const show = ref(false);
const longQuote = ref(false);

const getQuote = () => {
  const apiUrl =
    "https://type.fit/api/quotes/?method=getQuote&lang=en&format=json";
  show.value = true;
  fetch(apiUrl)
    .then((response) => {
      if (response.ok) {
        return response.json();
      }
    })
    .then((data) => {
      let number = Math.floor(Math.random() * data.length);
      const randomQuoteAuthor = data[number].author;
      const randomQuoteText = data[number].text;
      quote.value = randomQuoteText;
      checkQuoteLength();
      quoteAuthor.value = randomQuoteAuthor ? randomQuoteAuthor : "Unknown";
      show.value = false;
    });
};

const tweetQuote = () => {
  const twitterUrl = `https://twitter.com/intent/tweet?text=${quote.value} - ${quoteAuthor.value}`;
  window.open(twitterUrl, "_blank");
};

const checkQuoteLength = () => {
  longQuote.value = quote.value.length > 120;
};

const addLongQuoteClass = () => {
  return {
    "long-quote": longQuote.value,
  };
};

getQuote();
</script>

<style scoped>
@import "./QuoteComponent.css";
</style>
