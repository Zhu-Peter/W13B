<template>
  <div id="app">
    <VueGrid/>
  </div>
</template>

<script>
import VueGrid from './components/VueGrid.vue'

export default {
  name: 'App',
  components: {
    VueGrid
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
