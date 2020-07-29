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
import { eventBus } from '@/main.js';
export default {
  name: 'app',
  data() {
    return {
      countries: [],
      selectedCountry: null
    };
  },

  mounted() {
    fetch('https://restcountries.eu/rest/v2/all')
    .then(response => response.json())
    .then(data => this.countries = data)
    eventBus.$on('country-selected', (country) => {
      this.selectedCountry = country;
    })
  }, 

  components: {
    "countries-list": CountriesList
  }
}
</script>

<style>

</style>