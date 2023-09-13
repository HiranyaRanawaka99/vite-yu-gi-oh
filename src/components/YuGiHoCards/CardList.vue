<script >

import { store } from '../../data/store';

import SingleCard from './SingleCard.vue';


export default {
  data() {
    return {
    store,
    }
  },

  components: 
   { SingleCard }
}
</script>

<template>
  <section>
    <div class="row g-4 row-cols-2 row-cols-md-3 row-cols-lg-4">
      <SingleCard
      v-for="gameCard in store.gameCards"
      :key="gameCard.id"
      :gameCard = "gameCard"
      >
      </SingleCard>

    </div>
  </section>
</template>

<style lang="scss">

</style>
