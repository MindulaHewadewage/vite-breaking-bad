<script>
import axios from 'axios';
import { apiUri } from './data/index';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
    components: { AppHeader, AppMain },
    data() {
        return {
            store, apiUri
        }
    },
    methods: {
        fetchPokemon() {
            axios.get(apiUri)
                .then(res => {
                    const apiPokemons = res.data.docs;
                    store.pokemons = apiPokemons.map(pokemon => {
                        const { imageUrl, number, name, type1 } = pokemon;
                        return {
                            imageUrl,
                            number,
                            name,
                            type1
                        }
                    })
                })
        }
    },
    created() {
        this.fetchPokemon()
    }
}
</script>

<template>
    <app-header></app-header>
    <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>   