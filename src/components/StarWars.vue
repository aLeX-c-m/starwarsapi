<template>
<div>
<button v-bind:aria-label="height ? 'Hide Height' : 'Reveal Height'" v-on:click="height = !height">Height</button>
<button v-bind:aria-label="mass ? 'Hide Mass' : 'Reveal Mass'" v-on:click="mass = !mass">Mass</button>
<button v-bind:aria-label="eyecolor ? 'Hide Eye Color' : 'Reveal Eye Color'" v-on:click="eyecolor = !eyecolor">Eye Color</button>
<button v-bind:aria-label="haircolor ? 'Hide Hair Color' : 'Reveal Hair Color'" v-on:click="haircolor = !haircolor">Hair Color</button>
<button v-bind:aria-label="birthyear ? 'Hide Birth Year' : 'Reveal Birth Year'" v-on:click="birthyear = !birthyear">Birth Year</button>
  
  <ul>StarWars:
  <div v-for="war in wars" v-bind:key="war.url">
  <StarWar v-bind:war="war" v-bind:showheight= "height" v-bind:showmass="mass" v-bind:showeyecolor="eyecolor" v-bind:showhaircolor="haircolor" v-bind:showbirthyear="birthyear"></StarWar>
  </div>
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
        height: false,
        haircolor: false,
        eyecolor: false,
        birthyear: false
      };
    },
    created: function() {
      axios
        .get('https://swapi.co/api/people')
        .then(res => {
          console.log('results from api/people call', res.data.results)
          this.wars = res.data.results;
        })
    },
    components: {
      StarWar
    },
    methods: {
      greet: (text) => {
        axios.post('/', text)
        console.log('posted')
      }
    }
  }
</script>
