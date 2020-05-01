<template>
<div class="digit-display">
  <LedDigit v-for="(char, index) in displayLength" :key="index" :letter="toDisplay[index]"/>
</div>

</template>

<script>
import LedDigit from './LedDigit'
import digits from '../digits.js'
import Vue from 'vue';
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
    },
    count: {
      type: Number
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
    toDisplay () {
      const arr = this.computedChars.map((item,index)=> {
        const slice = item[0]
        console.log(slice)
        item = digits.blank;
        item.splice(-1,1,slice);
        console.log(item)
        return item
      });
      // return arr;
      return this.computedChars;
    },
    blanks () {
      return Array.from({ length: this.displayLength }, (v, i) => digits.blank)
    },
    computedChars () {
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