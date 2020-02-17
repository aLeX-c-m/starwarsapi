<template>
<div>
<button v-on:click="height = !height"> Height</button>
<button v-on:click="mass = !mass"> Mass</button>
<button v-on:click="eyecolor = !eyecolor"> Eye Color</button>
<button v-on:click="haircolor = !haircolor"> Hair Color</button>
<button v-on:click="birthyear = !birthyear"> Birthyear</button>
  
  <ul>StarWars:
  <div id="submission">
  <br>
  name:
  <input type="text" name="name" />
  <br>
  height: 
  <input type="text" name="height" />
  <br>
  mass: 
  <input type="text" name="mass" />
  <br>
  eye color:
  <input type="text" name="eye color" />
  <br>
  hair color:
  <input type="text" name="hair color" />
  <br>
  birth year:
  <input type="text" name="birth year" />
  <br>
  <input id="button" type="submit" value="add new character" />
  </div>
  <li v-for="war in wars" v-bind:key="war.url">
  <StarWar v-bind:war="war" v-bind:showheight= "height" v-bind:showmass="mass" v-bind:showeyecolor="eyecolor" v-bind:showhaircolor="haircolor" v-bind:showbirthyear="birthyear"></StarWar>
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
          this.wars = res.data.results;
        })
    },
    components: {
    StarWar
  }
  }
</script>
