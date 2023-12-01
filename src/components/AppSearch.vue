<script>
import { store } from "../store.js"

export default {
    name: "AppSearch",
    data() {
        return {
            store,
        }
    },
    methods: {
        searchPostalCode() {
            this.$emit("search");
        }
    },
    mounted() {
    }
}
</script>

<template>
    <div>
        <input placeholder="Type postal code" v-model="store.searchString">
        <button @click="searchPostalCode">Find</button>
    </div>
</template>

<style scoped></style>