<template>
  <g class=tableInput>

  </g>
</template>

<script>

import inputField from './inputField.vue'
import { createApp  } from 'vue'

export default {
  name: 'tableInput',

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
    this.pe = this.pathElement
    this.pe.onclick = this.handleClick

  },
  methods: {
    addFields(){
      for (var el=0; el < this.inputElements.length; el++){
        var pathSegments = this.inputElements[el].pathSegList

        var inputX = pathSegments.getItem(0).x
        var inputY = pathSegments.getItem(0).y
        var width = pathSegments.getItem(1).x

        var ns = 'http://www.w3.org/2000/svg'



       var wrapper = document.createElementNS(ns, "svg")
        createApp(inputField, {"field":0, "x":inputX, "y":inputY, "width":width}).mount(wrapper)
        document.querySelector( 'svg' ).appendChild(wrapper)
        this.fields.push(wrapper)
      }
      console.log(this.fields)
      
    },

    handleClick(){
      if (this.clicked == false){
        this.addFields()
        this.clicked = true
      }
      else {
        this.removeFields()
        this.clicked = false
      }
    },



    removeFields(){
      for (var el=0; el < this.fields.length; el++){
        this.fields[el].remove()
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>



</style>

