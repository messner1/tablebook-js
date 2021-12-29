<template>
  <div class="tablePage">
    <regionTest id="page">

    </regionTest>
  </div>
</template>

<script>
//sub components for each type of path input
import { createApp  } from 'vue'
import regionTest from '../../public/testregions3.svg'
import tableInput from './tableInput.vue'



export default {
  name: 'tablePage',
  components: {
    regionTest,

  },
  data (){
    return {
      groupElements: null,
    }
  },
  mounted: function() {

    var ns = 'http://www.w3.org/2000/svg'

    this.groupElements = document.getElementsByClassName("inputGroup")
    for (var el=0; el < this.groupElements.length; el++){
      
      var groupSubElements = this.groupElements[el].getElementsByTagName('path')
      var inputFields = []

      //console.log(groupSubElements)
      for (var sgel=0; sgel < groupSubElements.length; sgel++){
        //create template apps based on classname schema? why ids not working
        if(groupSubElements[sgel].attributes.class.value.includes("tableLoc")){
          console.log (groupSubElements[sgel].attributes.class)
          var inputRect = groupSubElements[sgel]
        }
        else if (groupSubElements[sgel].attributes.class.value.includes("inputLoc")){
          inputFields.push(groupSubElements[sgel])
        }
      }

      //var inputRect = this.groupElements[el].getElementsByClassName("tableLoc")
      //var inputFields = this.groupElements[el].getElementsByClassName("inputLoc")

      var wrapper = document.createElementNS(ns, "svg")
      createApp(tableInput, {"pathElement":inputRect, "inputElements":inputFields}).mount(wrapper)

    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.tablePage {
  height: 50%;
  width:  50%;
}
</style>

<style>

  path {
    fill:#FFFFFF;
    opacity:1.000000e-02;
  }
</style>