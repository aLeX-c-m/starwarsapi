<template>
  <ul>{{ war.name }}
  <li v-if="height"> {{ showheight }}</li>
  <li v-if="mass"> {{ showmass }}</li>
  </ul>
</template>

<script>

  export default {
    name: 'StarWar',
    props: ['war', 'showheight', 'showmass']
  }
</script>
