<script>
import axios from 'axios'
export default {
name: 'PokemonList',
data() {
    return {
        pokemons: []
    }
},
created() {
    axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1')
    .then((res) => {
        this.pokemons = res.data.docs;
    })
}
};

</script>

<template>
  <section id="pokemon">
    <div class="row g-3 row-cols-3">
        <div v-for="pokemon in pokemons" @key="pokemon.id">
        {{ pokemon.name }}
        </div>
    </div>
  </section>
</template>

<style lang="scss" scoped >
    @use '../../assets/scss/style.scss' as *;
</style>
