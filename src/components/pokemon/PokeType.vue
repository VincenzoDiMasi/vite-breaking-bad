<script>
export default {
    name:'PokeType',
    data () {
        return {
            types : [
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
            ]
        }
    }
}
</script>


<template>
    <select class="form-select w-25" aria-label="Default select example">
        
        <option  selected>All</option>
        <option v-for="type in types"> {{type}} </option>

    </select>

</template>



<style lang="scss" scoped>
select {
            margin: 20px auto;
            text-align: center;
            
    }
</style>