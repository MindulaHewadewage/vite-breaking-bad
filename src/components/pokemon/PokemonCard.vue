<script>
import { colorMap } from '../../data'
export default {
    name: 'PokemonCard',
    props: {
        imageUrl: String,
        number: Number,
        name: String,
        type1: String
    },
    computed: {
        bgColor() {
            return colorMap[this.type1]
        }
    }
}
</script>


<template>
    <div class="pokemon-card" :style="`background-color:${bgColor}`">
        <div class="pokemon-image">
            <img :src="imageUrl" :alt="name">
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
    text-align: center;
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