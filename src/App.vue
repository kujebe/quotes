<template>
  <div class="container">
    <ProgressBar :quoteCount="quotes.length" :maxQuotes="maxQuotes"/>
    <NewQuote @quoteAdded="pushQuote"/>
    <quoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"/>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          <span>Info:</span> Click on quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";
import ProgressBar from "./components/Header.vue";
export default {
  data() {
    return {
      quotes: ["First wonderful quote"],
      maxQuotes: 10
    };
  },
  components: {
    QuoteGrid,
    NewQuote,
    ProgressBar
  },
  methods: {
    pushQuote(quote) {
      if (quote) {
        if (this.quotes.length >= this.maxQuotes) {
          return alert("Maximun quotes reached, Delete quote first");
        }
        this.quotes.push(quote);
      }
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
.alert span {
  font-weight: bold;
}
</style>
