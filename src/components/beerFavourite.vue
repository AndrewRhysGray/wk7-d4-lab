<template>
<div>
<h3>Your favourite beers:</h3>
  <ul>
      <li v-for="beer in favebeers">{{ beer.name }}</li>
  </ul>
  </div>
</template>

<script>
export default {
name: 'beer-favourite',
props: ['favebeers']
}
</script>

<style>

</style>