<script setup>
import AktorFilmowy from './AktorFilmowy.vue';
defineProps({tytulFilmu:String});
</script>

<template>
 <p>
 Tytuł: {{ tytulFilmu }}
</p>
<p>
<AktorFilmowy/>
</p>
</template>