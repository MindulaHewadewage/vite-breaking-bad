<script>
export default {
    data() {
        return {
            types: [
                "Fairy",
                "Fire",
                "Flying",
                "Normal",
                "Dragon",
                "Steel",
                "Poison",
                "Electric",
                "Fighting",
                "Rock",
                "Dark",
                "Psychic",
                "Grass",
                "Ice",
                "Ghost",
                "Water",
                "Ground",
                "Bug"
            ]
        }


    }
}
</script>

<template>
    <select name="type" id="">
        <option v-for="type in types" :value="type">{{ type }}</option>
    </select>
</template>

<style>

</style>