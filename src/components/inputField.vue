<template>

     <foreignObject v-bind:x="x" v-bind:y="y" v-bind:width="width" height="40" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility">
        <body xmlns="http://www.w3.org/1999/xhtml">
          <input type="text" v-model="field" />
        </body>
    </foreignObject>

</template>

<script>


export default {
  name: 'inputField',
  props: ['x','y','width'],

  data (){
    return {
      field: null,
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  input {
    background: transparent;
  }

</style>

