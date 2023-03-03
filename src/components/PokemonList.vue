<template>
    <div class="flex space-x-4 overflow-scroll">
        <Pokemon :pokemon="pokemon" v-for="(pokemon, index) in pokemons" :key='index'/>
        <!-- use span tag for element visibility -->
        <!-- <div ref="target">{{ targetIsVisible }}</div> -->
    </div>
    <div class="float m-3 area shadow-lg">
        <!-- <span v-text="targetIsVisible"></span> -->
  </div>
</template>

<script setup>
// import pokemons from '@/assets/sampledataset.json'
import Pokemon from './Pokemon.vue'

import { useElementVisibility } from '@vueuse/core';
import {ref, onMounted} from 'vue'
import client from '@/assets/apiclient.js'


console.log(targetIsVisible)


const pokemons = ref([])

onMounted(()=>{
    client.get("/pokemon/").then(res => {
        console.log("response receieved", res.data)
        pokemons.value = res.data
    }).catch(errors =>{
        console.log("error", errors)
    })
})

//mount and then make api call
// import axios from 'axios';
// // import { onMounted, ref, watch, onUpdated } from 'vue';

// const pokemons = ref()

// const props = defineProps(['limit'])

// const limit = ref()
// limit.value = props.limit

// const target = ref()
// const targetIsVisible = useElementVisibility(target)
// onMounted(()=>{
//     axios.get(`https://pokeapi.co/api/v2/pokemon?limit=${props.limit}`).then(data =>{
//         pokemons.value = data.data.results
//     })
// })

// onUpdated((limit)=>{
//     axios.get(`https://pokeapi.co/api/v2/pokemon?limit=${props.limit}`).then(data =>{
//         pokemons.value = data.data.results
//     })
// })



</script>
