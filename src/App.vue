<script>
import AppCard from './components/AppCard.vue'
import axios from 'axios';
import { store } from "./store.js"
export default {
  components: {
    AppCard
  },
  data() {
    return {
		store,
    }
  },
  mounted() {
  },
  methods: {

  }
}
</script>

<template></template>

<style scoped></style>