<template>
<div>
<button v-on:click="height = !height">Height</button>
<button v-on:click="mass = !mass">Weight</button>
  <ul>StarWars:
  <li v-for="war in wars" v-bind:key="war.url">
  <StarWar v-bind:war="war" v-bind:showheight= "height" v-bind:showmass="mass" ></StarWar>
  </li>
  </ul>
  </div>
</template>

<script>
 import axios from 'axios';
 import StarWar from './StarWar.vue';

  export default {
    name: 'StarWars',
    data() {
      return {
        wars: null,
        mass: false,
        height: false
      };
    },
    created: function() {
      axios
        .get('https://swapi.co/api/people')
        .then(res => {
          this.wars = res.data.results;
        })
    },
    components: {
    StarWar
  }
  }
</script>
