<script setup>
    import cars from "../data/cars.json";
    import { RouterLink } from "vue-router";
</script>

<template>
    <div>
        <h1 class="title"> HomeView </h1>
        <div class="cars">

            <!-- http://localhost:5173/cars/3 -->
            <RouterLink :to="`/cars/${car.id}`" v-for="car in cars" :key="car.id" href=""> 
                {{ car.name  }}
            </RouterLink>
        </div>
    </div>
</template>

<style scoped>

    .title {
        display: flex;
        justify-content: center;
    }
    .cars {
        display: flex;
    }

    .cars a {
        height: 100px;
        width: 100%;
        text-decoration: none;
        color: black;
        box-shadow: 1px 1px 10px black;
        margin: 10px;
        display: flex;
        align-items: center;
        justify-content: center;
    }
</style>