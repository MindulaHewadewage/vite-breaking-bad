<script>
export default {
    name: 'PokemonCard',
    props: {
        image: String,
        number: Number,
        name: String,
        type1: String
    }
}
</script>


<template>

    <div class="pokemon-card ">
        <div class="pokemon-image">
            <img :src="image" :alt="name">
        </div>
        <div class="pokemon-description">
            <p>{{ number }}</p>
            <h3>{{ name }}</h3>
            <p>{{ type1 }}</p>
        </div>
    </div>

</template>

<style>

</style>