<script >
import axios from 'axios';
import { store } from './data/store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';


export default {
  data() {
    return {
      store,
      apiUri: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
    }   
  },
      
  methods: {
    fetchGameCards(endpoint) {
      axios.get(endpoint)
      .then((response) => {
        console.log(response.data.data)
        const gameCardData= response.data.data.map((gameCard) => {
          const { card_images, name, archetype, } = gameCard
          return {
            image: card_images[0].image_url,
            name,
            archetype
          }
        })
        store.gameCards = gameCardData;
      });
    }
  },

  created() {
      this.fetchGameCards(this.apiUri)
  },

  components: { AppHeader, AppMain }

}
</script>

<template>
  <AppHeader></AppHeader>
  
  <AppMain></AppMain>
</template>

<style lang="scss">
@use './assets/styles/general.scss';


</style>
