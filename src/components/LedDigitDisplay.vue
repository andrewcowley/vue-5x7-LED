<template>
<div class="digit-display">
  <LedDigit v-for="(char, index) in displayLength" :key="index" :letter="computedChars[index]"/>
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
    displayLength: {
      type: Number
    },
    message: {
      type: String
    }
  },
  computed: {
    arrayOfChars () {
      const arrayOfChars = this.message.split('');
      return arrayOfChars;
    },
    truncatedChars () {
      return this.arrayOfChars.slice(0, this.displayLength);
    },
    computedChars () {
      // console.log(this.arrayOfChars, this.truncatedChars)
      return this.truncatedChars.map((item)=>{
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