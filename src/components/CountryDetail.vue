<template>
    <div class="country-detail" v-if="country">
        <h2>{{ country.name }} </h2>
        <h3>Capital</h3>
        <p>{{ country.capital }} </p>
        <h3>Population</h3>
        <p>{{ country.population }} </p>
    </div>
</template>

<script>
export default {
    name: 'country-detail',
    props: ['country']
}
</script>

<style>
    .country-detail {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin: auto;
        margin-top: 50px;
        width: 35%;
        height: 400px;
        background-color: #ffffff;
        border-radius: 15px;
        border: solid 1px #4ac4b9;
    }

    h3 {
        color: #37948c;
        font-style: oblique;
    }

    h2 {
        color: #003a35;
        text-transform: uppercase;
    }
</style>