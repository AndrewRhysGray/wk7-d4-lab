<template>
  <article v-if="beer">
      <h3>{{ beer.name }}</h3>
      <p>Alcohol level is {{ beer.abv }}</p>
      <img :src="beer.image_url" alt="Can't display beer">
  </article>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style>

</style>