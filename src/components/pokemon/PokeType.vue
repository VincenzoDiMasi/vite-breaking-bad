<script>
export default {
    name:'PokeType',
    data () {
        return {
            genres : [
                        "Bug",
                        "Dark",
                        "Dragon",
                        "Fighting",
                        "Fairy",
                        "Fire",    
                        "Steel",
                        "Normal",
                        "Electric",
                        "Poison",     
                        "Rock",
                        "Ghost",
                        "Psychic",
                        "Grass",
                        "Ice",
                        "Flying",
                        "Water",
                        "Ground"
            ],
            type: ''
        }
    },
    emits: ['change-type'],
    
}
</script>


<template>
       <select v-model="type" @change="$emit('change-type', type)" class="form-select w-25" aria-label="Default select example">
        <option selected>All</option>
        <option v-for="genre in genres"> {{genre}} </option>

    </select>

</template>



<style lang="scss" scoped>
select {
            margin: 20px auto;
            text-align: center;
            
    }
</style>