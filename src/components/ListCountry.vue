<template lang="html">
  <div>
    <li>{{country.name}}</li>
  </div>
</template>

<script>
export default {
  name: 'list-country',
  props: ['country']
}
</script>

<style lang="css" scoped>
</style>
