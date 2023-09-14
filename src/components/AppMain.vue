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

  <div class="container main mt-5">

    <CardList></CardList>

  </div>
  
</template>

<style lang="scss" scoped>
.main.container {
  background-color: white;
}

</style>
