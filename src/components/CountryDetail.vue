<template>
    <div v-if="country">
        <h2>Name: {{ country.name }} </h2>
        <p>Capital: {{ country.capital }} </p>
        <p>Population: {{ country.population }} </p>
    </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>

</style>