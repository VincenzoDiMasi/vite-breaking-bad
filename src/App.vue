<script>
import axios from 'axios';
import {store} from './data/store.js';
import AppMain from './components/AppMain.vue';
import PokeType from './components/pokemon/PokeType.vue';

export default {
    components: {AppMain, PokeType},
    data() {
    return {
        store
    }
},
methods: {
  fetchPokemons(url){
    axios.get(url)
    .then((res) => {
        store.pokemons = res.data.docs;
    })
  }
},
created() {
    this.fetchPokemons(store.apiUri)
}
};

</script>

<template>
  <header class="container d-flex justify-content-center">
    <img id="logo-header" src="./assets/img/logo-pokedex.png" alt="">
  </header>
  <PokeType></PokeType>
  <AppMain ></AppMain>
</template>

<style lang="scss" >
@use './assets/scss/style.scss' as *;

#logo-header {
  height: 180px;
}
</style>
