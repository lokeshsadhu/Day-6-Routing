<script setup>
import {useRoute, useRouter} from "vue-router"
import {onMounted,ref} from "vue"
import cars from "../data.json"

const route = useRoute()
const router = useRouter()
const car = ref(null)
const {id} = route.params
console.log(id)

onMounted(() => {
   const c = cars.find(c => c.id === parseInt(id));
   car.value = c
})
console.log(car)

</script>

<template>
    <div class="container">
        <div v-if="car">
            <h1>The Car</h1>
            <p>Make: {{car.make}}</p>
            <p>Body: {{car.body}}</p>
            <p>Price: {{car.price}}</p>
            <p>Year: {{car.year}}</p>
            <button @click="router.push(`/`)">Go Back</button>
            <RouterView />
        </div>
        <div v-else>
            <h1>Car not found</h1>
            <button @click="router.back()">Go Back</button>
        </div>
    </div>
</template>

<style scoped>
.container {
  max-width: 800px;
  margin: auto;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
  background-color: #fff;
  color: #333;
  text-align: center;
  transition: box-shadow 0.3s ease-in-out;
}

.container:hover {
  box-shadow: 0 12px 20px rgba(0, 0, 0, 0.2);
}

h1 {
  font-size: 2.5rem;
  color: #333;
  margin-bottom: 20px;
  font-weight:bold;
}

p {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

button {
  background-color: #007bff;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s ease-in-out;
}

button:hover {
  background-color: #0056b3;
}

button + button {
  margin-left: 10px;
}

h1:not(:first-child) {
  font-size: 2rem;
  color: #d9534f; 
}

button:not(:first-child) {
  background-color: #d9534f;
}

button:not(:first-child):hover {
  background-color: #c9302c;
}
</style>
