<script setup>
import { ref } from 'vue';
import { listaProdutos } from '@/data/produtos';
import { formataPreco } from '@/utils/produtoUtils';
const produtos = ref(listaProdutos);
produtos.value = produtos.value.filter(p => p.categoria === 'Alimentos')

</script>

<template>
<div class="container">

    <h1>alimentos</h1>
    <div class="produtos">
        <div v-for="p in produtos" :key="p.id" class="produto-card">
            <img :src="p.imagem" :alt="p.nome" class="produto-imagem">
            <h2>{{ p.nome }}</h2>
            <p>preço:{{ formataPreco(p.preco) }}</p>
        </div>
    </div>
</div>
</template>

<style scoped>

</style>