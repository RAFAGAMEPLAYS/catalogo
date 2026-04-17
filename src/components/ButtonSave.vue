<script setup>
defineEmits(['salvar']);
</script>
<template>
<button @click.prevent="$emit('salvar')">
    <slot>
        
    </slot>
</button>

</template>
<style scoped>

</style>