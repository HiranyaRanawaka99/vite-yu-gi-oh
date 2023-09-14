<script >
import axios from 'axios';
import { store } from './data/store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/YuGiHoCards/AppLoader.vue';
import Select from './components/ui/Select.vue';


export default {
  data() {
    return {
      store,
      apiUri: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0',
      apiUriArchetypes: 'https://db.ygoprodeck.com/api/v7/archetypes.php',
      isLoading: false,
    }   

  },
      
  methods: {
    fetchGameCards(endpoint) {

      this.isLoading = true;

      axios
      .get(endpoint)
      .then((response) => {
        // console.log(response.data.data)
        const gameCardData= response.data.data.map((gameCard) => {
          const { card_images, name, archetype, } = gameCard
          return {
            image: card_images[0].image_url,
            name,
            archetype
          }
        })
        store.gameCards = gameCardData;

      })

      .catch((error) => {
        console.error(error)
        store.gameCards = [];
      })

      .finally (() => {
        this.isLoading = false;
      })
    },
    
    fetchArchetypes(api) {
      axios
      .get(api)
      .then((response)=> {
        const archetypesData = response.data.map((archetype) => {
          return archetype.archetype_name;
        })
        store.archetypes = archetypesData
      })
    }
  },

  created() {
      this.fetchGameCards(this.apiUri);
      this.fetchArchetypes(this.apiUriArchetypes);
  },

  components: { AppHeader, AppMain, AppLoader, Select}

  }

</script>

<template>
  
  <AppLoader
  v-if="isLoading"
  loadingText = "Loading Game Cards"
  />

  <AppHeader/>

  <Select 
  :archetypes = "store.archetypes"
  cardTypeSelect = "Choose archetype"
  > </Select>  


  <AppMain/>

</template>

<style lang="scss">
@use './assets/styles/general.scss';


</style>
