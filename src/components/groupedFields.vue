<template>
  <g class=groupedFields>

  </g>
</template>

<script>

import inputField from './inputField.vue'
import { createApp  } from 'vue'

export default {
  name: 'groupedFields',

  //components: {inputField},

  props: ['pathElement', 'inputElements'],

  data (){
    return {
      fields: [],
      pe: null,
      clicked: false
    }
  },
  mounted: function() {

  },
  methods: {
    

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



</style>

