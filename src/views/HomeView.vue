<template>
<main class="container">
    <h1>OUR CARS</h1>
    <div class="cards">
    <div
        v-for="car in cars"
        :key="car.id"
        class="card"
        @click="router.push(`/car/${car.id}`)"
    >
        <h2>{{ car.make }}</h2>
        <h3>${{ car.price }}</h3>
    </div>
    </div>
</main>
</template>

<script setup>
import { ref } from "vue";
import carsData from "../data.json";
import { useRouter } from "vue-router";

const router = useRouter();
const cars = ref(carsData);
</script>

<style scoped>
    .container {
    text-align: center;
}

h1 {
    font-size: 2.5rem;
    color: #333;
    margin-bottom: 30px;
}

.cards {
    display: flex;
    width: 100%;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.card {
    background-color: #f8f9fa; 
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 20px;
    width: 200px;
    cursor: pointer;
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
    transition: background-color 0.3s ease-in-out;
}

.card:hover {
    background-color: #e9ecef;
}

h2 {
    font-size: 1.5rem;
    color: #343a40; 
    margin-bottom: 10px;
}

h3 {
    font-size: 1.2rem;
    color: #007bff; 
    margin: 0;
}

.links {
    padding: 20px;
}

.links a {
    margin: 0 5px;
}
</style>
  