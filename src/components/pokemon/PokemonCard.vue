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

    <div class="pokemon-card p-2 col">
        <div class="pokemon-image">
            <img :src="image" :alt="name">
        </div>
        <div class="pokemon-description p-2">
            <p>#{{ number }}</p>
            <p class="fw-bolder ">{{ name }}</p>
            <p class="fst-italic">{{ type1 }}</p>
        </div>
    </div>

</template>

<style scoped lang="scss">
.pokemon-card {
    background-color: lightgrey;
    display: flex;
    flex-direction: column;
    text-align: center;
    margin: 20px;
    border-radius: 10px;

}

.pokemon-image img {
    width: 100px;
    height: 100px;
    border-radius: 50%;
}

p {
    margin-bottom: 0.5rem;
}
</style>