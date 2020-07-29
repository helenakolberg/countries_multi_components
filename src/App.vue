<template>
  <div>
    <h1>Countries</h1>
    <div>
      <countries-list :countries='countries' />
    </div>
        <div>
      <country-detail :country="selectedCountry" />
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
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
    "countries-list": CountriesList,
    "country-detail": CountryDetail
  }
}
</script>

<style>

</style>