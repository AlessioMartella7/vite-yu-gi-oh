<script>
export default {
  data() {
    return {
      
    }
  },
  props: {
    cardObj: {
      type: Object,
      required: true,
    }
  },
}
</script>

<template>
<div class="col">
    <div class="card">
      <img :src="cardObj.card_images[0].image_url_small" class="card-img-top" alt="...">
      <div class="card-body">
      <p class="card-text">{{ cardObj.name }}</p>
      </div>
    </div>
</div>
</template>

<style scoped>
</style>