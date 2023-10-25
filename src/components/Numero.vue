<script setup>
const props = defineProps(['titulo']);
const emit = defineEmits();
</script>

<template>
    <div class="card col-md-4 text-center border-0">
        <h3 class="card-title">{{ titulo }}</h3>
        <input class="rounded-pill card-body text-center" @input="evento => emit('update:modelValue', evento.target.value)"
            type="number" placeholder="0">
    </div>
</template>
