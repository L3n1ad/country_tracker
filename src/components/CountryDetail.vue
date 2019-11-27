<template lang="html">
  <div v-if='country'>
    <h2>Name: {{country.name}}</h2>
    <p>Population: {{country.population}}</p>
    <p>Capital: {{country.capital}}</p>
    <p>
      Languages:
      <li v-for='(language, index) in country.languages'>
        {{language['name']}}
      </li>
    </p>
    <img :src="country.flag" style="max-width: 300px">
  </div>
</template>

<script>
export default {
  name: 'country-detail',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
