<template>
  <div>
      <select name="country" id="country" v-model="selectedCountry">
          <option v-for="(country, index) in countries" :country="country" :key="index" v-bind:value="country"></option>
      </select>
  </div>
</template>

<script>
export default {
    name: 'country-select',
    props: ['countries'],
    methods: {
        handleChange() {
            eventbus.$emit('country-selected', this.country)
        }
    }
}
</script>

<style>

</style>