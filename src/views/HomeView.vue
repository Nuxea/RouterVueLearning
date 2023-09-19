<script setup>
import cars from "@/data/cars.json"
</script>

<template>
  <div>
    <h1>Cars</h1>
    <div class="cars">
      <RouterLink :to="`/cars/${car.id}`" v-for="car in cars" :key="car.id"  class="card">
        <img :src="car.img" :alt="car.name">
        <div class="card-text">
          <h2>{{ car.name }}</h2>
        </div>

      </RouterLink>
    </div>
  </div>
</template>

<style scoped>
.cars {
  display: flex;
  gap: 10px;
}

.card {
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(0,0,0,0.7);
  margin: auto auto 35px 20px;
  cursor: pointer;
  text-decoration: none;
}

.card img {
  width: 100%;
  height: 190px;
  margin: 0;
  object-fit: cover;
}

.card .card-text {
  text-align: center;
  padding: 0 5px;
  background-color: #fff;
  color: #3b3b3b;
}

.card .card-text:hover {
  transition: 0.3s;
  background-color: #3b3b3b;
  color: #fff;
}

.card .card-text h2 {
  font-weight: bold;
}
</style>