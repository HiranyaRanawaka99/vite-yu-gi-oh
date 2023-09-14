<script>

export default {
    data() {
        return {
            selectedOption: '',
        }
    },

    props: {
        archetypes: Array,
        cardTypeSelect: String,
    },

    emits: ['selected-option'],
}

</script>


<template>
    <div class="container select">
    <select 
        @change = "$emit('selected-option', selectedOption)"
        class="form-select" 
        aria-label="Default select example">
        <option selected> {{ cardTypeSelect || 'Choose an option' }}</option>
        <option 
        v-for="archetype in archetypes"
        value="1"> {{ archetype }}</option>
    </select>
</div>
        

</template>


<style lang="scss" scoped>
.select {
    width: 250px;
    margin-left: 6rem;
}

</style>