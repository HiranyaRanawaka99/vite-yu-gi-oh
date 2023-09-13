<script >
import CardList from './YuGiHoCards/CardList.vue';

export default {
  data() {
    return {}
  },

  components : {CardList}

}
</script>

<template>

  <div class="main container">

    <CardList></CardList>

  </div>
  
</template>

<style lang="scss" scoped>
.main.container {
  background-color: antiquewhite;
}

</style>
