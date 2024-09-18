<script>
import AppMainCardsHolderCard from './AppMainCardsHolderCard.vue';

export default {
  components:{
      AppMainCardsHolderCard
  },
  data() {
      return {
      
    }
  }
}
</script>

<template>
  <section id="card-holder">
    <div class="search-result" >
      <div>Search Result</div>
    </div>
    <AppMainCardsHolderCard/>
  </section>
  
</template>

<style lang="scss" scoped>
.search-result {
  background-color: #232429;
  height: 80px;

}
#card-holder {
  background-color: #fff;
  height: 700px;

}
</style>