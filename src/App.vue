<script>
import AppMain from './components/AppMain.vue'

export default {
    components: {AppMain}
};

</script>

<template>
  <header class="container d-flex justify-content-center">
    <img id="logo-header" src="./assets/img/logo-pokedex.png" alt="">
  </header>
  <AppMain></AppMain>
</template>

<style lang="scss" >
@use './assets/scss/style.scss' as *;

#logo-header {
  height: 180px;
}
</style>
