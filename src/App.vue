<script>
import axios from 'axios';
import { store } from './data/store';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
export default {
    components: { AppHeader, AppMain },
    data() {
        return {
            store
        }
    },
    methods: {
        fetchPokemon() {
            axios.get('https://41tyokboji.execute-api.eu-central-1.amazonaws.com/dev/api/v1/pokemons?per=12&page=1')
                .then(res => {
                    store.pokemons = res.data.docs;
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