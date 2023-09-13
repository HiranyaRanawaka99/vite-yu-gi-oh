<script >
export default {
  props: {
    gameCard: Object,
  }

}
</script>

<template>
  <div class="col game-card">
    <div class="card-img">
      <img 
        :src="gameCard.image" 
        />
    </div>
    <div class="card-info">
      <h4>{{ gameCard.name }}</h4>
      <h6>{{ gameCard.archetype }}</h6>
    </div>
  </div>

  
</template>

<style lang="scss" scoped>
  .game-card {
  
    .card-info {
      background-color: goldenrod;
      padding:  .5rem .8rem 1rem;
      text-align: center;
    }
  }

</style>
