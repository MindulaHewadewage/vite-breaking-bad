<script>
import { store } from '../data/store';
import BaseSelect from './pokemon/BaseSelect.vue'
export default {
    name: 'AppHeader',
    components: { BaseSelect },
    emits: ['filter-change'],
    data() {
        return store
    }
};
</script>

<template>
    <header>
        <div class="container">
            <div class="filter">
                <base-select :options="types" default-value="All"
                    @option-change="$emit('filter-change', $event)"></base-select>

            </div>

            <div class="pokemon-logo">
                <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/98/International_Pok%C3%A9mon_logo.svg/2560px-International_Pok%C3%A9mon_logo.svg.png"
                    alt="pokemon logo">
            </div>
        </div>

    </header>
</template>

<style scoped lang="scss">
.container {
    display: flex;
    align-items: center;
    justify-content: space-between;
}



.pokemon-logo img {
    width: 200px;
    padding: 20px 0;

}
</style>   