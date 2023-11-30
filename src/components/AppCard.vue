<script>
export default {
    name: "AppCard",
    props: {
        info: Object
    }
}
</script>

<template>
    <div class="card">
            <h2>Brewery name:</h2>
            <p>{{ info.name }}</p>
            <h4>Address:</h4>
            <p> {{ info.address_1 }}</p>
            <h4>Postal code: </h4>
            <p>{{ info.postal_code }}</p>
        </div>
</template>

<style scoped>
</style>