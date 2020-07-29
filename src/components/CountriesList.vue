<template>
    <div>
        <li v-for="country in countries">{{ country.name }}</li>
    </div>
</template>

<script>
export default {
    name: 'countries-list',
    props: ['countries']
}
</script>

<style>

</style>