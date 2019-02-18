<template>
  <div class="row">
    <form action>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label for="quote">Quote</label>
        <textarea class="form-control" cols="3" rows="4" v-model="quote"></textarea>
      </div>

      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn btn-primary" @click.prevent="addQuote">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
//import { eventBus } from "../main";
export default {
  name: "NewQuote",
  data() {
    return {
      quote: ""
    };
  },
  methods: {
    addQuote() {
      this.$emit("quoteAdded", this.quote);
      //eventBus.createQuote(this.quote);
      this.quote = "";
    }
  }
};
</script>

<style>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
}
.quote {
  cursor: pointer;
}
.quote:hover {
  background: #ffe2e2;
}
</style>
