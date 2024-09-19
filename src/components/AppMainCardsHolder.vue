<script>
import AppMainCardsHolderCard from './AppMainCardsHolderCard.vue';
import axios from 'axios';
import {store} from '../store.js'
import AppMainCardsHolderLoader from './AppMainCardsHolderLoader.vue';
import AppMainSelect from './AppMainSelect.vue';


export default {
  components:{
      AppMainCardsHolderCard,
      AppMainCardsHolderLoader,
      AppMainSelect
  },
  data() {
      return {
      archObject: [],  
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=45&offset=0',
      apiArchetypeUrl: 'https://db.ygoprodeck.com/api/v7/archetypes.php',
    }
  },
  methods:{
      getCards (){
        axios.get(this.apiUrl)
        .then((response) => {
          store.cardList = response.data.data;
        })
      },
      getArchetypeList (){
        axios.get(this.apiArchetypeUrl)
        .then((response)=> {
        this.archObject = response.data;
        })
      },
      searchByArchetype (message){
        // axios.get(this.apiArchetypeUrl, message)
        // .then((response)=> {
       console.log('STAMPA search By Archetype',message )
      }
  },

  created(){
    setTimeout(this.getCards,2000);
    this.getArchetypeList();
  },
}
</script>

<template>
  <AppMainSelect
  :archetypeName="archObject"
  @archetype-select="searchByArchetype"
  />
  <section id="card-holder" class="bg-white p-4">
    <AppMainCardsHolderLoader v-if="store.cardList.length === 0 "/>
    <div v-else class="container">
      <div class="row row-cols-5 justify-content-center mt-0" >
        <div class="col-12">
          <div class="search-result py-4 ps-3" >
            <p class="text-white fw-bold">Search Result</p>
        </div>
      </div>
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

</style>