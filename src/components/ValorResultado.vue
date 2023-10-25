<script setup>
const props = defineProps(['resultado']);
</script>

<template>
    <div class="col-md-4 justify-content-center d-flex">
        <div class="card border-0" style="width: 18rem;">
            <h2 class="text-center">Resultado</h2>
            <h3 class="card-body rounded-pill border border-info text-center">{{ resultado }}</h3>
        </div>
    </div>
</template>
