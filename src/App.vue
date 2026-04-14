<script setup>
import produtoChild from './components/produtoChild.vue';
import { ref } from 'vue'
const produtos = ref([
{ id: 1, nome: 'Ração Premium Cães', preco: 120, categoria: 'Alimentos' },
{ id: 2, nome: 'Ração Gatos Castrados', preco: 95, categoria: 'Alimentos' },
{ id: 3, nome: 'Petisco Natural', preco: 18, categoria: 'Alimentos' },
{ id: 4, nome: 'Brinquedo Bola', preco: 22, categoria: 'Brinquedos' },
{ id: 5, nome: 'Mordedor de Corda', preco: 30, categoria: 'Brinquedos' },
{ id: 6, nome: 'Shampoo Pet', preco: 35, categoria: 'Higiene' },
{ id: 7, nome: 'Tapete Higiênico', preco: 42, categoria: 'Higiene' },
{ id: 8, nome: 'Coleira Azul', preco: 28, categoria: 'Acessórios' },
{ id: 9, nome: 'Guia de Passeio', preco: 40, categoria: 'Acessórios' }
])
const preco=ref(0);
const posicaoProduto=ref(-1);
const alterando=ref(false);
function corrigirPreco(idProduto,precoProduto){
  preco.value=precoProduto;
  posicaoProduto.value=idProduto;
  posicaoProduto.value=produtos.value.findIndex(p => p.id === idProduto);
  alterando.value=true;
}
function salvarPreco(){
  produtos.value[posicaoProduto.value].preco = preco.value;
  alterando.value=false;
}
</script>

<template>
<div class="container">
<h1>catalogo de produtos</h1>
  <div>
    <ul>
      <produtoChild v-for="produto in produtos" :key="produtos.id" :nome="produto.nome" :categoria="produto.categoria" :preco="produto.preco">
        <button @click.prevent="corrigirPreco(produto.id,produto.preco)">corrigir preço</button>
      </produtoChild>
    </ul>
  </div>
  <div v-show="alterando">
    <label>preço</label>
    <input type="text" v-model="preco">
    <button @click="salvarPreco()">salvar</button>
    <button></button>
    
  </div>
</div> 
</template>

<style scoped>

</style>
