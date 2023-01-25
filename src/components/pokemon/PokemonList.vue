<script>
import {store} from '../../data/store';
import PokemonCard from './PokemonCard.vue';


export default {
name: 'PokemonList',
components: {PokemonCard},
data() {
    return {
        store
    }
},


};

</script>

<template>
  <section id="pokemon">
    <div class="row g-3 row-cols-3">
        <PokemonCard 
        v-for="pokemon in store.pokemons" 
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
