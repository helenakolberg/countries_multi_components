<template>
  <div>
    <h1>Countries</h1>
  </div>
</template>

<script>
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
  }
}
</script>

<style>

</style>