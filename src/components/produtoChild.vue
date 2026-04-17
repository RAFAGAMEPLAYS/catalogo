<script setup>
defineProps(['nome','categoria','preco','id'])
defineEmits(['corrigirpreco'])
import ButtonChild from './ButtonChild.vue';
import { formataPreco } from '@/utils/produtoUtils';
</script>

<template>
  <li>
    {{ nome }} -  {{ formataPreco(preco) +"R$" }} ({{ categoria }})
    <ButtonChild @clique="$emit('corrigirpreco',id,preco)">
      corrigir preço
    </ButtonChild>
  </li>
</template>

<style scoped>

</style>