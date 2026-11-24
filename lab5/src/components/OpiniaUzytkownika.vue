<script setup>
import {ref, onMounted, onUpdated, onBeforeUnmount} from 'vue';

const opinia = ref("");

onMounted(() => {
    if (localStorage.getItem('opinia') !== null){
 opinia.value = localStorage.getItem('opinia');
    }
    else opinia.value = "";
});
onBeforeUnmount(() => {
 localStorage.setItem('opinia', opinia.value);
});
onUpdated(() => {
 localStorage.setItem('opinia', opinia.value);
});

</script>

<template>
<div>
 <h1>Opinia użytkownika</h1>
 <input v-model="opinia" placeholder="Wpisz opinię">
 <p>Twoja opinia: {{ opinia }}</p>
</div>
</template>