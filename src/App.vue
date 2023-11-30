<script>
import AppCard from "./components/AppCard.vue";
import axios from "axios";
import { store } from "./store.js";
export default {
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
  mounted() {
    this.getBreweries();
  },
  methods: {
    getBreweries() {
      axios.get(this.store.apiUrl).then((result) => {
        this.store.breweries = result.data.results;
      });
    },
  },
};
</script>

<template></template>

<style scoped></style>
