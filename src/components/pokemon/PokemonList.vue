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
        <div class="pokemon-list row g-3">
            <pokemon-card v-for="pokemon in pokemons" :key="pokemon.name" v-bind="pokemon"
                class="col-12 col-sm-6 col-md-4 col-lg-3">

            </pokemon-card>

        </div>
    </div>
</template>

<style scoped lang="scss"></style>