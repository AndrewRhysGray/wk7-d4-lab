<template>
  <div id="app">
    <beer-list :beers='beers' ></beer-list>
    <beer-detail :beer='selectedBeer'></beer-detail>
  </div>
</template>

<script>
import beerList from "./components/beerList.vue";
import { eventBus } from './main.js'
import beerDetail from "./components/beerDetail.vue"

export default {
  name: "app",
  data() {
    return {
      beers: [],
      selectedBeer: {}
    }
  },
  components: {
    "beer-list": beerList,
    "beer-detail": beerDetail
  },

  mounted() {
    fetch("https://api.punkapi.com/v2/beers")
      .then(beersData => beersData.json())
      .then(beers => (this.beers = beers));

      eventBus.$on('beer-selected', (beer) => {
        this.selectedBeer = beer;

      })
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
