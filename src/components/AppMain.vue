<script>
import AppMainCardsHolder from './AppMainCardsHolder.vue';
import AppMainSearch from './AppMainSearch.vue';

export default {
  components: {
      AppMainCardsHolder,
      AppMainSearch
    },
  data() {
      return {
      
    }
  }
}
</script>

<template>
<main>
  <div class="container">
<AppMainSearch/>
<AppMainCardsHolder/>
</div>
</main>
</template>

<style lang="scss" scoped>

main {
  background-color: #D48F3B;
  height: 1200px;
  padding-top: 5rem;
}

</style>