<script>
export default {
    name: 'BaseSelect',
    data() {
        return {
            selectedOption: ''
        }
    },
    emits: ['option-change'],
    props: {
        defaultValue: String,
        options: Array
    }
};

</script>

<template>
    <select v-model="selectedOption" @change="$emit('option-change', selectedOption)">
        <option value="">{{ defaultValue || '---' }}</option>
        <option v-for="option in options" :key="option" :value="option">{{ option }}</option>
    </select>
</template>

<style></style>