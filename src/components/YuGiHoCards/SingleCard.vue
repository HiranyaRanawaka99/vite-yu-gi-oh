<script >
export default {
  props: {
    gameCard: Object,
  }

}
</script>

<template>
  <div class="col">
    <div class="game-card">
        <img 
          :src="gameCard.image" 
          />
        <h4>{{ gameCard.name }}</h4>
        <h6>{{ gameCard.archetype }}</h6>
      
  </div>
  </div>

  
</template>

<style lang="scss" scoped>
  .game-card {
      background-color: goldenrod;
      text-align: center;
      
      padding: 0;
      height: 100%;
  
  }

</style>
