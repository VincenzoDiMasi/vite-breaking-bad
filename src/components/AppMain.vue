<script>
import PokemonList from './pokemon/PokemonList.vue';
export default {
name: 'AppMain',
components: {PokemonList},

};

</script>

<template>
  <main class="container ">
    <PokemonList ></PokemonList>
  </main>
</template>

<style lang="scss" scoped >
    @use '../assets/scss/style.scss' as *;

    main {
        border: 50px solid rgb(193, 0, 0);
        border-radius: 20px;
        min-height: 500px
    }

</style>
