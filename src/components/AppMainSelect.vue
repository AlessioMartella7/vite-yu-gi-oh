<script>
export default {

  data() {
    return {
      
    }
  },
  props: {
    archetypeName:{
      type: Array,
      Required:true,
    },
  } 

}

</script>

<template>
  <select class="form-select mb-5 w-25" aria-label="Default select example" >
  <option v-for="(arch,index) in archetypeName" :value="index" >{{ arch.archetype_name }}

  </option>
  
</select>
</template>

<style scoped>
</style>