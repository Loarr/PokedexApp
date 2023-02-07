<template>
    <div class="flex w-max space-x-4 overflow-scroll">
        <Pokemon :pokemon="pokemon" v-for="(pokemon, index) in pokemons" :key='index'/>
    </div>
</template>

<script setup>
// import pokemons from '@/assets/sampledataset.json'
import Pokemon from './Pokemon.vue'
import axios from 'axios';
import { onMounted, ref } from 'vue';

const pokemons = ref()

//mount and then make api call
onMounted(()=>{
    axios.get('https://pokeapi.co/api/v2/pokemon?limit=151').then(data =>{
        pokemons.value = data.data.results
        console.log(pokemons.value)
    })
})

</script>
