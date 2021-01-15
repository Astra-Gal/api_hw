<template>
  <div id="app">
    <h1>Adventures in the Rijksmuseum</h1>

  </div>
</template>

<script>
import config from '../config.js'

export default {
  name: 'App',
  data() {
    return {
      things: [],
      selectedThing: null
    }
  },
  components: {
// components go here
  },
  mounted() {
    fetch(`https://www.rijksmuseum.nl/api/en/collection?key=Yye8TNJH&q=Doll+house&imgonly=True`)
    .then(response => console.log(response.json()))

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
</style>
