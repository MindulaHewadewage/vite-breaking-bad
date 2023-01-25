<script>
export default {
    name: 'PokemonCard',
    props: {
        number: Number,
        name: String,
        type1: String
    }
}
</script>


<template>

    <div v-for="pokemon in pokemons" :key="pokemon.number" class="pokemon-card ">
        <div class="pokemon-image">
            <img :src="pokemon.imageUrl" :alt="pokemon.name">
        </div>
        <div class="pokemon-description">
            <p></p>
            <h1>{{ pokemon.name }}</h1>
            <p></p>
        </div>
    </div>

</template>

<style>

</style>