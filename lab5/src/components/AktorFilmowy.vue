<script setup>
import {inject} from 'vue';
const imie = inject('imieAktora');
const nazwisko = inject('nazwiskoAktora')

</script>

<template>
<div>Aktor: {{imie}} {{nazwisko}}</div>
</template>