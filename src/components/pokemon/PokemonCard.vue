<script>
// import axios from 'axios'
export default {
name: 'PokemonCard',
props:{
    image: String,
    number: Number,
    name: String,
    type1: String,
},
data() {
    
},
};

</script>

<template>
 <div class="align-items-center p-4 card">
                <img :src="image" alt="">
                <div> #{{ number }} </div>
                <h2> {{ name }} </h2>
                <div class="fw-bold">  {{ type1 }} </div>
            </div>
</template>

<style lang="scss" scoped >
    @use '../../assets/scss/style.scss' as *;

    img {
        height: 100px;
        width: 100px;
    }
</style>
