<script>
export default {
  data() {
    return {
      
    }
  }
}
</script>

<template>
<div class="loader"></div>
</template>

<style lang="scss" scoped>
/* HTML: <div class="loader"></div> */
.loader {
  display: inline-grid;
  width: 120px;
  aspect-ratio: 1;
  clip-path: polygon(100% 50%,85.36% 85.36%,50% 100%,14.64% 85.36%,0% 50%,14.64% 14.64%,50% 0%,85.36% 14.64%);
  background: #574951;
  animation: l1 6s infinite linear;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate (-50%,-50%);
}
.loader:before,
.loader:after {
  content:"";
  grid-area: 1/1;
  background: #83988E;
  clip-path: inherit;
  margin: 10%;
  animation: inherit;
  animation-duration: 12s;
}
.loader:after {
  background: #BCDEA5;
  margin: 20%;
  animation-duration: 18s;
}
@keyframes l1 {to{rotate: 1turn}}
</style>