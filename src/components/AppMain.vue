<script>
import PokemonList from './pokemon/PokemonList.vue'
export default {
    components: { PokemonList }
}
</script>

<template>
    <main class="container">
        <div class="pokedex-container">
            <pokemon-list></pokemon-list>
        </div>
    </main>
</template>

<style scoped lang="scss">
main {

    min-height: 600px;
    background-color: #DADFDD;
    margin-top: 20px;
    border-radius: 20px;
}

.container {
    display: flex;
    align-items: center;

    .pokedex-container {
        width: 95%;
        height: 550px;
        background-color: #50565B;
        margin: 0 auto;

        overflow-y: auto;
    }
}
</style>