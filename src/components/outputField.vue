<template>

     <foreignObject v-bind:x="x" v-bind:y="y" v-bind:width="width" height="80" requiredFeatures="http://www.w3.org/TR/SVG11/feature#Extensibility">
        <body xmlns="http://www.w3.org/1999/xhtml">
          <p> {{outputValue}} </p>
        </body>
    </foreignObject>

</template>

<script>


export default {
  name: 'outputField',
  props: ['outputValue'],

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
    background: white;
  }

</style>

