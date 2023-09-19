<script setup>
import {useRoute, useRouter} from "vue-router";
  import cars from "@/data/cars.json"

  const route = useRoute()
  const router = useRouter()
  // console.log(route.params)
  const carId = parseInt(route.params.id)
  const car =  cars.find(c => c.id === carId)

const showContact = () => {
    // if (carId === 4) return;
    return router.push(`/cars/${carId}/contact`);
}
</script>

<template>
  <div v-if="car" class="card">
    <img :src="car.img" :alt="car.name">
    <div class="card-text">
      <h2>{{ car.name }}</h2>
      <p>Year: {{ car.year }}</p>
      <p>Price: {{ car.price }}$</p>

      <button @click="showContact" class="button">Click for Contact</button>
    </div>
    <div class="contact">
      <RouterView />
    </div>
  </div>
  <div v-else>
    <h1>Car not found</h1>
  </div>

</template>

<style scoped>
.card {
  width: 90%;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0,0,0,0.7);
  margin: auto auto 35px 20px;
}

.card img {
  width: 100%;
  height: 500px;
  margin: 0;
  object-fit: cover;
}

.card .card-text {
  padding: 0 5px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
}

.card .card-text h2 {
  font-weight: bold;
}

.card .button {
  padding: 10px;
  border: none;
  border-radius: 5px;
  width: 100%;
  cursor: pointer;
}

.card .button:hover {
  transition: 0.3s;
  background-color: #3b3b3b;
  color: #fff;
}

.contact {
  display: flex;
  flex-direction: column;
  align-items: end;
  padding: 3%;
}
</style>