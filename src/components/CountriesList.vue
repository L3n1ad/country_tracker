<template lang="html">
  <div>
    <list-country v-for='(country, index) in countries' :country='country' :key='index'></list-country>
  </div>
</template>

<script>
import ListCountry from './ListCountry.vue'

export default {
  name: 'countries-list',
  props: ['countries'],
  components: {
    'list-country': ListCountry
  }
}
</script>

<style lang="css" scoped>
</style>
