<template>
  <div id="app">
    <LedDigitDisplay :to-display="'CD 01'" :digits="12"/>
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
  margin-top: 60px;
}
</style>
