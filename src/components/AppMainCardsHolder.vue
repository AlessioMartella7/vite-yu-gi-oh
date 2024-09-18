<script>
import AppMainCardsHolderCard from './AppMainCardsHolderCard.vue';
import axios from 'axios';
import {store} from '../store.js'

export default {
  components:{
      AppMainCardsHolderCard
  },
  data() {
      return {
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0',
    }
  },
  methods:{
      getCards (){
        axios.get(this.apiUrl)
        .then((response) => {
          // console.log(response.data)
          store.cardList = response.data.data;
        })
      }
  },
  created(){
    this.getCards();
  },
}
</script>

<template>
  <section id="card-holder">
    <div class="search-result py-4 ps-3" >
        <p class="text-white fw-bold">Search Result</p>
    </div>
    <div class="container">
      <div class="row row-cols-5 justify-content-center" >
          <AppMainCardsHolderCard v-for="card in store.cardList" :key=card.id
            :cardObj="card"
          />
      </div>
  </div>
  </section> 
  
</template>

<style lang="scss" scoped>
.search-result {
  background-color: #232429;
  height: 80px;

}
#card-holder {
  background-color: #fff;


}
</style>