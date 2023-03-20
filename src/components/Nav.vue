<script setup>
    // RouterLink faz com que o componente se mantenha no mesmo estado
    // mesmo depois de navegar para outra rota.
    import { RouterLink } from "vue-router";
</script>

<template>
    <div>
        <RouterLink active-class="active" to="/"> Home </RouterLink>
        <RouterLink active-class="active" to="/about"> About </RouterLink>


        <a href="https://youtu.be/I_xLMmNeLDY"> The Ultimate Vue 3 Tutorial </a>
    </div>
</template>

<style scoped>
    .active {
    font-weight: 900;
    color: rgb(181, 128, 31);
    }

    div {
        display: flex;
        margin: 10px;
    }

    div a {
        padding: 10px;
    }

</style>