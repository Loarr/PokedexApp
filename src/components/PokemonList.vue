<template>
    <div class="flex w-100% space-x-4 overflow-scroll">
        <Pokemon :pokemon="pokemon" v-for="(pokemon, index) in pokemons" :key='index'/>
    </div>
</template>

<script setup>
// import pokemons from '@/assets/sampledataset.json'
import Pokemon from './Pokemon.vue'
import axios from 'axios';
import { onMounted, ref } from 'vue';

const pokemons = ref()

const limit = defineProps(['limit'])

//mount and then make api call
onMounted(()=>{
    axios.get(`https://pokeapi.co/api/v2/pokemon?limit=${limit.limit}`).then(data =>{
        pokemons.value = data.data.results
    })
})

</script>
