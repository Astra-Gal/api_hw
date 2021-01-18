<template>
  <div id="app" v-if="dollsHouses">
    <h1>Adventures in the Rijksmuseum</h1>
    <h2>Choose your adventure...</h2>
    <dolls-houses :dollshouses="dollsHouses"></dolls-houses>

  </div>
</template>

<script>
import DollsHouses from './components/DollsHouses.vue'

export default {
  name: 'App',
  data() {
    return {
      dollsHouses: null,
      selectedThing: null
    }
  },
  components: {
    'dolls-houses': DollsHouses
  },
  mounted() {
    fetch(`https://www.rijksmuseum.nl/api/en/collection?key=TYyQYD1w=Doll+house&imgonly=True&toppieces=True`)
    .then(response => response.json())
    .then(dollsHouses => this.dollsHouses = dollsHouses.artObjects)
    // .then((response) => {
    //   let artObjects = map(response.artObjects,)
    //   console.log(response.json())})

  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h2, h3 {
    font-family: 'Antic Didone', serif;
}

</style>
