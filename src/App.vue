<template>
  <div>
    <h1>Countries</h1>
    <div>
      <countries-list :countries='countries' />
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'
export default {
  name: 'app',
  data() {
    return {
      countries: [] 
    };
  },

  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.countries = data)
  }, 

  components: {
    "countries-list": CountriesList
  }
}
</script>

<style>

</style>