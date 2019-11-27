<template lang="html">
  <div>
    <select v-model='selectedCountry' v-on:change='handleSelected'>
      <!-- <option disabled selected value="">Select Country</option> -->
      <list-country v-for='(country, index) in countries' :country='country' :key='index'></list-country>
    </select>
  </div>
</template>

<script>
import ListCountry from './ListCountry.vue';
import {eventBus} from '../main.js'

export default {
  name: 'countries-list',
  data(){
    return {
      selectedCountry: null
    }
  },
  props: ['countries'],
  methods: {
    handleSelected(){
      eventBus.$emit('dropdown-country-selected', this.selectedCountry)
    }
  },
  components: {
    'list-country': ListCountry
  }
}
</script>

<style lang="css" scoped>
</style>
