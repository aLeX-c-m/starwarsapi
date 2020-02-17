<template>

  <ul>
  <li style="text-decoration: bold" >{{ war.name }}</li>
  <li v-if="showheight">Height: {{ war.height }}</li>
  <li v-if="showmass">Mass: {{ war.mass }}</li>
  <li v-if="showeyecolor">Eye Color: {{ war.eye_color }}</li>
  <li v-if="showhaircolor">Hair Color: {{ war.hair_color }}</li>
  <li v-if="showbirthyear">Birth Year: {{ war.birth_year }}</li>
  </ul>
</template>

<script>
  
  export default {
    name: 'StarWar',
    props: ['war', 'showheight', 'showmass', 'showhaircolor', 'showeyecolor', 'showbirthyear']
  }
</script>
