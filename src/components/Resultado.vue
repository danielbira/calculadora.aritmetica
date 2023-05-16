<script setup>
    const props = defineProps (['resultado', 'numero1', 'numero2'])
</script>

<template>
    <span v-if="props.numero1 && props.numero2 !=''" ><h2>Resultado: {{ props.resultado }}</h2></span>
    <span v-else-if="props.numero1 || props.numero2 ===''"><h2>Digite os dois numeros</h2></span>
</template>