<template>
  <ul>StarWars:
  <li >{{wars}}</li>
  </ul>
</template>

<script>
 import axios from 'axios';

  export default {
    name: 'StarWars',
    data() {
      return {
        wars: null,
      };
    },
    created: function() {
      axios
        .get('https://swapi.co/api/people')
        .then(res => {
          this.wars = res.data;
        })
    }
  }
</script>
