<template lang="html">
  <div>
    <select v-model='selectedCountry'>
      <list-country v-for='(country, index) in countries' :country='country' :key='index'></list-country>
    </select>
  </div>
</template>

<script>
import ListCountry from './ListCountry.vue'

export default {
  name: 'countries-list',
  data(){
    return {
      selectedCountry: null
    }
  },
  props: ['countries'],
  components: {
    'list-country': ListCountry
  }
}
</script>

<style lang="css" scoped>
</style>
