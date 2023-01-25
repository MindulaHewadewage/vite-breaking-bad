<script>
import axios from 'axios';
import PokemonCard from './PokemonCard.vue'
export default {
    name: 'PokemonList',
    components: { PokemonCard },
    data() {
        return {
            pokemons: []
        }
    },

    created() {
        axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=10&page=1')
            .then(res => {
                this.pokemons = res.data.docs;
            })
    }

}
</script>


<template>
    <div class="row g-4 row-cols-5">
        <pokemon-card v-for="pokemon in pokemons" :key="pokemon.name" class="pokemon-list" :image="pokemon.imageUrl"
            :number="pokemon.number" :name="pokemon.name" :type1="pokemon.type1">

        </pokemon-card>

    </div>

</template>

<style scoped lang="scss">

</style>