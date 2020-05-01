<template>
  <div id="app">
    <LedDigitDisplay
      :count="count"
      :message="'There are way too many characters here'"
      :display-length="12"
    />
    <button @click="count++">count: {{ count }}</button>
  </div>
</template>

<script>
import LedDigitDisplay from "./components/LedDigitDisplay.vue";

export default {
  name: "app",
  components: {
    LedDigitDisplay,
  },
  data() {
    return {
      count: 0,
    };
  },
};
</script>

<style>
#app {
  margin-top: 60px;
}
</style>
