<script setup>
defineProps(['nome','categoria','preco'])
</script>

<template>
  <li>
    {{ nome }} - R$ {{ preco }} ({{ categoria }})
  </li>
</template>

<style scoped>

</style>