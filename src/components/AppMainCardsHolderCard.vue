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
<div class="col my-3">
    <div class="card h-100">
      <img :src="cardObj.card_images[0].image_url_small" class="card-img-top" :alt="cardObj.name">
      <div class="card-body d-flex flex-column justify-content-center align-items-center text-center">
      <p class="card-text text-white text-uppercase fw-bold">{{ cardObj.name }}</p>
      <p class="card-archetype">{{ cardObj.archetype }}</p>
      </div>
    </div>
</div>
</template>

<style lang="scss" scoped>

.card-body {
  background-color: #D48F3B;
}

</style>