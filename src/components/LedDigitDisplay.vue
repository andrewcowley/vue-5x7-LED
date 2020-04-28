<template>
<div class="digit-display">
  <LedDigit v-for="(digit, index) in computedDigits" :key="index" :letter="computedDigits[index]"/>
</div>

</template>

<script>
import LedDigit from './LedDigit'
import digits from '../digits.js'
export default {
  name: 'LedDigitDisplay',
  components: {
    LedDigit
  },
  props: {
    digits: {
      type: Number
    },
    toDisplay: {
      type: String
    }
  },
  computed: {
    arrayOfDigits () {
      return this.toDisplay.split('')
    },
    computedDigits () {
      return this.arrayOfDigits.map((item)=>{
        const charCode = digits[item.charCodeAt()];
        if(charCode) {
          return digits[item.charCodeAt()]
        }
        return digits['unknown']
    })
    }
  }
}
</script>

<style>
.digit-display {
  display: flex;
}
</style>