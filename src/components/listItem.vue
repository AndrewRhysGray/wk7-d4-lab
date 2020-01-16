<template>
  <li v-on:click="handleClick">{{ beer.name }}
      <button v-on:click="addFavourite">Add to favourites</button>
  </li>
</template>

<script>
import { eventBus } from '../main.js'
export default {
    name: 'list-item',
    props: ['beer'],
    methods: {
        handleClick() {
            eventBus.$emit('beer-selected', this.beer)
        },
        addFavourite() {
            eventBus.$emit('beer-favourite', this.beer)
        }
    }

}
</script>

<style>

</style>