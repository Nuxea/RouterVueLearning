<script setup>

  import {useRoute} from "vue-router";
  import cars from "@/data/cars.json"

  const route = useRoute()
  const car = cars.find(c => c.id === parseInt(route.params.id))
</script>

<template>
  <div v-if="car">
    <h1>Contact</h1>

    <p><span>Seller Name:</span> {{ car.contact.dealer}}</p>
    <p><span>Number:</span> {{ car.contact.number}}</p>
  </div>

</template>

<style scoped>
span {
  font-weight: bold;
}
</style>