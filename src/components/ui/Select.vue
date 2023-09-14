<script>

export default {
    data() {
        return {
            
        }
    },

    props: {
        archetypes: Array,
        cardTypeSelect: String,

    }
}

</script>


<template>
    <div class="container select">
    <select 
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