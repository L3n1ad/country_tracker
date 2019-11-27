<template lang="html">
  <div>
    <countries-list :countries='countries'></countries-list>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue'

export default {
  name: 'app',
  data(){
    return {
      countries: [],
      selectedCountry: null
    }
  },
  mounted(){
    fetch('https://restcountries.eu/rest/v2/all')
    .then(resolt => resolt.json())
    .then(countries => this.countries = countries)
  },
  components: {
    'countries-list': CountriesList
  }
}
</script>

<style lang="css" scoped>
</style>
