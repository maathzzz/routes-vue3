<script setup>
    // Composables
    import { useRoute, useRouter, RouterView } from "vue-router";
    import cars from "../data/cars.json";
    
    const route = useRoute();
    // router.push
    const router = useRouter();

    const carId = parseInt(route.params.id);
    const car = cars.find(c => c.id === parseInt(route.params.id))

    // const showContact = () => {
    //     if(carId === 4) return;
    //     return router.push(`/cars/${carId}/contact`)
    // }

</script>

<template>
    <div v-if="car" class="container">
        <h1> {{ car.name }} </h1>
        <div class="card">
            <p>{{ car.name }}</p>
            <p> Ano: {{ car.year }}</p>
            <p>{{ new Intl.NumberFormat('pt-BR', { style: 'currency', currency: 'BRL' }).format(car.price) }}</p>
            <button @click="router.push(`/cars/${carId}/contact`)"> Contact Info </button>

            <!-- Rendering Contact Info -->
            <RouterView />
        </div>
    </div>
    <!-- Adding not found -->
    <div v-else>
        <h1> Car Not Found 404</h1>
    </div>
</template>

<style scoped>
    .container h1 {
        display: flex;
        justify-content: center;
    }

    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
</style>