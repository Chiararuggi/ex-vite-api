<script>
import AppCard from "./components/AppCard.vue";
import AppSearch from "./components/AppSearch.vue"

import axios from "axios";
import { store } from "./store.js";
export default {
  components: {
    AppCard,
    AppSearch,
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
      let url = this.store.apiUrl;

      if (this.store.searchString.length) {
				url = `https://api.openbrewerydb.org/v1/breweries?by_postal=${this.store.searchString}&per_page=10`;
        
			}

      axios.get(url).then((result) => {
        this.store.breweries = result.data;
      });
    },
  },
};
</script>

<template>
  <AppSearch @search="getBreweries()" />
  <AppCard v-for="brewery in store.breweries" :info="brewery" />
  <p v-if="store.breweries.length == 0">No brewery found</p>
</template>

<style scoped></style>
