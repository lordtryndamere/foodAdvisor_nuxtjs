<template>
  <div class="container">
    <RestaurantCard />
  </div>
</template>

<script>
import RestaurantCard from '../components/RestaurantCard'
export default {
  components: {
    RestaurantCard,
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}


</style>
