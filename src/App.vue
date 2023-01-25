<script>
import axios from 'axios';
import AppMain from './components/AppMain.vue'

export default {
    components: {AppMain},
    data() {
    return {
        pokemons: []
    }
},
methods: {
  fetchPokemons(){
    axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=12&page=1')
    .then((res) => {
        this.pokemons = res.data.docs;
    })
  }
},
created() {
    this.fetchPokemons()
}
};

</script>

<template>
  <header class="container d-flex justify-content-center">
    <img id="logo-header" src="./assets/img/logo-pokedex.png" alt="">
  </header>
  <AppMain :pokemons="pokemons"></AppMain>
</template>

<style lang="scss" >
@use './assets/scss/style.scss' as *;

#logo-header {
  height: 180px;
}
</style>
