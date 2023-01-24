<script>
import axios from 'axios'
import PokemonCard from './PokemonCard.vue'
export default {
name: 'PokemonList',
components: {PokemonCard},
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
        <PokemonCard 
        v-for="pokemon in pokemons" 
        :image="pokemon.imageUrl"
        :number="pokemon.number"
        :name="pokemon.name" 
        :type1="pokemon.type1" 
        @key="pokemon.id">
        
        </PokemonCard>
    </div>
  </section>
</template>

<style lang="scss" scoped >
    @use '../../assets/scss/style.scss' as *;
</style>
