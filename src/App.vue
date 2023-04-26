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
        fetchPokemon(endpoint = apiUri) {
            axios.get(endpoint)
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
        },
        fetchTypes() {
            axios.get(apiUri + '/types1')
                .then(res => { store.types = res.data; })
                .catch(err => { console.error(err) });

        },
        filterPokemon(type) {
            const url = type ? `${apiUri}?eq[type1]=${type}` : apiUri;
            this.fetchPokemon(url)
        }
    },
    created() {
        this.fetchTypes();
        this.fetchPokemon();
    }
}
</script>

<template>
    <app-header @filter-change="filterPokemon"></app-header>
    <app-main></app-main>
</template>

<style lang="scss">
@use './assets/scss/style.scss'
</style>   