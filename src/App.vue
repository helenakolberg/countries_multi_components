<template>
  <div>
    <h1>Countries</h1>
    <div><country-select :countries='countries' /></div>
    <div><country-detail :country="selectedCountry" /></div>
  </div>
</template>

<script>
import CountrySelect from './components/CountrySelect.vue';
import CountryDetail from './components/CountryDetail.vue';
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
    "country-select": CountrySelect,
    "country-detail": CountryDetail
  }
}
</script>

<style>
  body {
    background-color: #ceeee3;
  }

  h1 {
    color: #003a35;
  }
</style>