<template lang="html">
  <div>
    <h1>Country Selector</h1>
    <div class='main-container'>
      <countries-list :countries='countries'></countries-list>
      <country-detail :country='selectedCountry'></country-detail>
    </div>
  </div>
</template>

<script>
import CountriesList from './components/CountriesList.vue';
import {eventBus} from './main.js';
import CountryDetail from './components/CountryDetail.vue'

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

    // eventBus.$on('country-selected', (country) => {
    //   this.selectedCountry = country;
    // })

    eventBus.$on('dropdown-country-selected', (country) => {
      this.selectedCountry = country;
    })
  },
  components: {
    'countries-list': CountriesList,
    'country-detail': CountryDetail
  }
}
</script>

<style lang="css" scoped>
  .main-container {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
</style>
