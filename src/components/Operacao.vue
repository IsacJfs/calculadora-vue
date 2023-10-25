<script setup>
const emit = defineEmits();
</script>

<template>
    <div class="card col-md-1 text-center align-self-center mt-5 border-0">
        <select class="card-title text-center rounded-pill p-2"
            @change="evento => emit('update:modelValue', evento.target.value)">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
            <option value="resto">%</option>
        </select>
    </div>
</template>
