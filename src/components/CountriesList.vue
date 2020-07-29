<template>
    <div>
        <list-item v-for="(country, index) in countries" :country="country" :key="index">{{ country.name }}</list-item>
    </div>
</template>

<script>
import ListItem from './ListItem.vue'

export default {
    name: 'countries-list',
    props: ['countries'],
    components: {
        "list-item": ListItem
    }
}
</script>

<style>

</style>