<script setup>
    const props = defineProps (['operacao', 'numero1', 'numero2'])
</script>

<template>
    <div class="operation">
        <h2>Selecione a operação</h2>
        <select class="m-4 p-2" @change="props.operacao">
            <option value="+">+</option>
            <option value="-">-</option>
            <option value="/">/</option>
            <option value="*">*</option>
        </select>
    </div>
    <div>
        <input @keyup="props.numero1" type="number" required placeholder="Digite o numero">
        <input @keyup="props.numero2" type="number" required placeholder="Digite o numero">
    </div>
</template>