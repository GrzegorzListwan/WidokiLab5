<script setup>
import {ref, provide} from 'vue'
import UlubionyFilm from './components/UlubionyFilm.vue';
import OcenaFilmu from './components/OcenaFilmu.vue';
import OpiniaUzytkownika from './components/OpiniaUzytkownika.vue';

const film = ref(null);

const tytul = ref("");
const imieAktora = ref("Jim");
const nazwiskoAktora= ref("Carrey");

provide('imieAktora', imieAktora);
provide('nazwiskoAktora', nazwiskoAktora);

const dynamicznyKomponent = ref(OcenaFilmu);

film.value = {
 tytul:"Głupi i głupszy",
 imieAktora: imieAktora, 
 nazwiskoAktora: nazwiskoAktora
}


function wymienFilm(tytul, imie, nazwisko)
{
if (tytul!=""){
 film.value.tytul = tytul,
 film.value.imieAktora = imie, 
 film.value.nazwiskoAktora = nazwisko
}
}

</script>
<template>
<UlubionyFilm :tytul-filmu="film.tytul"/>
<button @click = "wymienFilm(tytul, imieAktora, nazwiskoAktora)">Przeladuj</button>
<input v-model="tytul" placeholder="Dopisz nowy film">
<input v-model="imieAktora" placeholder="Wpisz imie aktora">
<input v-model="nazwiskoAktora" placeholder="Wpisz nazwisko aktora">
<button @click = "dynamicznyKomponent = OcenaFilmu">Ocena Filmu</button>
<button @click = "dynamicznyKomponent = OpiniaUzytkownika">Opinia Uzytkownika</button>

<KeepAlive>
<component :is="dynamicznyKomponent">
</component>
</KeepAlive>
</template>