<script setup>
import produtoCard from '@/components/produtoCard.vue';
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
      <produtoCard v-for="p in produtos" :key="p.id" :id="p.id" :nome="p.nome" :preco="p.preco" :categoria="p.categoria" :imagem="p.imagem"/>
    </div>
</div>
</template>

<style scoped>

</style>    