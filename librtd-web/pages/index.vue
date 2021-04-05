<template>
  <div>
    <textarea v-model="inputSequence" cols="30" rows="10"></textarea>
    <input type="number" v-model="kval" min="1">
    {{ inputSequence ? result : '' }}
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  data() {
    return {
      inputSequence: '',
      kval: 2,
    }
  },
  computed: {
    //? I forget how to do multiple computed statements
    kval() {
      try {
        return reverseComplementReturnTimeDistribution(this.inputSequence, this.kval)
      } catch (error) {
        return 'Invalid sequence'
      }
    },
    result() {
      try {
        return reverseComplementReturnTimeDistribution(this.inputSequence, this.kval)
      } catch (error) {
        return 'Invalid sequence'
      }
    },
  },
})
</script>
