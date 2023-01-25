<script>
import axios from 'axios';
import {store} from './data/store.js';
import AppMain from './components/AppMain.vue';
import PokeType from './components/pokemon/PokeType.vue';

export default {
    components: {AppMain, PokeType},
    data() {
    return {
        store,
        typeFilter: '',
        apiUri: 'https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons',
    }
},
methods: {
  fetchPokemons(url){
    axios.get(url)
    .then((res) => {
        store.pokemons = res.data.docs;
    })
  },

  onTypeChange (type){
    this.typeFilter = type;
    this.apiUri = `${this.apiUri}?eq[type1]=${this.typeFilter}`;
  }
},
created() {
    this.fetchPokemons(this.apiUri)
}
};

</script>

<template>
  <header class="container d-flex justify-content-center">
    <img id="logo-header" src="./assets/img/logo-pokedex.png" alt="">
  </header>
  <PokeType @change-type="onTypeChange"></PokeType>
  <AppMain ></AppMain>
</template>

<style lang="scss" >
@use './assets/scss/style.scss' as *;

#logo-header {
  height: 180px;
}
</style>
