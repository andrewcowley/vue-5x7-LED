<template>
  <div class="led-digit">
    <div class="row" v-for="(row, index) in letter" :key="index">
      <div class="led" v-for="(led, ledIndex) in row" :class="{ on: led }" :key="`${index}-${ledIndex}`"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LedDigit",
  props: {
    letter: {
      type: Array,
      default() {
        return [
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
          [0, 0, 0, 0, 0],
        ];
      },
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.led-digit {
  margin: 2px;
}
.row {
  display: flex;
  flex-direction: row;
}
.led {
  width: 5px;
  height: 5px;
  margin: 1px;
  background: #efefef;
}

.on {
  background: red;
}
</style>
