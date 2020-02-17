<template>

  <div>{{ war.name }}
  <li v-if="showheight">Height: {{ war.height }}</li>
  <li v-if="showmass">Mass: {{ war.mass }}</li>
  <li v-if="showeyecolor">Eye Color: {{ war.eye_color }}</li>
  <li v-if="showhaircolor">Hair Color: {{ war.hair_color }}</li>
  <li v-if="showbirthyear">Birthyear: {{ war.birth_year }}</li>
  </div>
</template>

<script>
  
  export default {
    name: 'StarWar',
    props: ['war', 'showheight', 'showmass', 'showhaircolor', 'showeyecolor', 'showbirthyear']
  }
</script>
