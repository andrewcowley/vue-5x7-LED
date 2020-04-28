<template>
  <div id="app">
    <LedDigitDisplay :to-display="'There are way too many characters here'" :digits="12"/>
  </div>
</template>

<script>
import LedDigitDisplay from './components/LedDigitDisplay.vue'

export default {
  name: 'app',
  components: {
    LedDigitDisplay
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
