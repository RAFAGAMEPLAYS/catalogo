<script setup>
import { RouterLink } from 'vue-router';
</script>
<template>
<header>
    <nav>
        <RouterLink to="/">Início</RouterLink>
        <RouterLink to="/alimentos">Alimentos</RouterLink>
        <RouterLink to="/bebidas">Bebidas</RouterLink>
    </nav>
</header>
</template>

<style scoped>
header{
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    z-index: 100;
    padding: 16px;
    border-bottom: 1px solid #ddd;
    box-sizing: border-box;
}
nav{
    display: flex;
    gap: 16px;
}
a{
    text-decoration: none;
    color: #333;
}
.router-link-active{
    font-weight: bold;
}
</style>