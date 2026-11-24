<script setup>
import {ref, onMounted, onUpdated, onBeforeUnmount} from 'vue';

const ocena = ref("");

onMounted(() => {
    if (localStorage.getItem('ocena') !== null){
 ocena.value = localStorage.getItem('ocena');
    }
    else ocena.value = "";
});

onUpdated(() => {
 localStorage.setItem('ocena', ocena.value);
});

onBeforeUnmount(() => {
 localStorage.setItem('ocena', ocena.value);
});
</script>

<template>
<div>
 <h1>Ocena filmu</h1>
 <input v-model="ocena" placeholder="Wpisz ocenę">
 <p>Twoja ocena: {{ ocena }}</p>
</div>
</template>