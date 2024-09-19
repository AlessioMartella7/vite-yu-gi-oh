<script>
export default {

  data() {
    return {
      searchedArchetype:'',
    }
  },

  props: {
    archetypeName:{
      type: Array,
      Required:true,
    },
  }, 

  methods:{
    filterByArchetype(message){
      this.$emit('archetypeSelect', message)
    },
  }

}

</script>

<template>
  <select v-model="searchedArchetype" class="form-select mb-5 w-25" aria-label="Default select example" >
  <option v-for="(arch,index) in archetypeName" :value="arch.archetype_name"  @click="filterByArchetype(searchedArchetype)">
    {{ arch.archetype_name }}
  </option>
  
</select>
</template>

<style scoped>
</style>