<script setup>
import ButtonSave from './components/ButtonSave.vue';
import produtoChild from './components/produtoChild.vue';
import { ref } from 'vue'
import { listaProdutos } from './data/produtos';
import { formataPreco } from './utils/produtoUtils';
const produtos=ref(listaProdutos);
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
      <produtoChild v-for="produto in produtos" :key="produtos.id" :nome="produto.nome" :id="produto.id" :categoria="produto.categoria" :preco="produto.preco" @corrigirpreco="corrigirPreco">
        
      </produtoChild>
    </ul>
  </div>
  <div v-show="alterando">
    <label>preço</label>
    <input type="text" v-model="preco" @keyup.enter="salvarPreco">
    <ButtonSave @click="salvarPreco"  @salvar="salvarPreco">
      salvar
    </ButtonSave>
    
    
  </div>
</div> 
</template>

<style scoped>

</style>
