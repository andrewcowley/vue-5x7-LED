<template>
  <div id="app">
    <LedDigitDisplay :message="'There are way too many characters here'" :digits="12"/>
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
