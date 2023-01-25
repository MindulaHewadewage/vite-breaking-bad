<script>

import { store } from '../../data/store';
import PokemonCard from './PokemonCard.vue'
export default {
    name: 'PokemonList',
    components: { PokemonCard },
    data() {
        return store
    }




}
</script>


<template>
    <div class="container">
        <div class="pokemon-list row row-cols-5">
            <pokemon-card v-for="pokemon in pokemons" :key="pokemon.name" :image="pokemon.imageUrl"
                :number="pokemon.number" :name="pokemon.name" :type1="pokemon.type1">

            </pokemon-card>

        </div>
    </div>


</template>

<style scoped lang="scss">
.pokemon-list {
    align-items: center;
    justify-content: center;
}
</style>