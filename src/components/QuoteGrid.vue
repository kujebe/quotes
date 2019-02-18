<template>
  <div class="row">
    <Quote
      v-for="(quote, index) in quotes"
      :key="quote"
      @click.native="deleteQuote(index)"
    >{{ quote }}</Quote>
  </div>
</template>

<script>
//import { eventBus } from "../main";
import Quote from "./Quote.vue";

export default {
  name: "QuoteGrid",
  props: ["quotes"],
  components: {
    Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
  /*created() {
    eventBus.$on("quoteCreated", quote => {
      this.quotes.push(quote);
    });
  }*/
};
</script>

