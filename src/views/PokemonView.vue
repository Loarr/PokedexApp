<template>
    <div class="flex flex-col space-y-6">
        <h1 class="text-6xl text-gray-900 font-semibold">{{ dispName }}</h1>
        <h2 class="text-4xl text-gray-900 font-semibold">{{ genus }}</h2>
        <div class="flex items-center space-x-4">
            <span>Weight</span><span>{{ pokemonDetails?.weight }}kg</span>
            <span>Height</span><span>{{ pokemonDetails?.height }}m</span>
        </div>
        <img :src="image" :alt="pokemonDetails?.name" class="w-64 h-64 rounded-lg" />
        <div class="flex space-x-4 items-center">
            <div class="">
                <TypeBar :pkmType="type1"/>
            </div>
            <div class="" v-if="type2">
                <TypeBar :pkmType="type2"/>
            </div>
        </div>
        <div>
            <span>{{ pokedex.flavor_text }}</span>
        </div>
    </div>
</template>

<script setup>

import {useRoute} from "vue-router";
// import pokemons from "@/assets/sampledataset.json";
import { onMounted, ref } from "vue";
import axios from "axios";
import TypeBar from "@/components/TypeBar.vue"


const route = useRoute()
const pkmName = ref("")
const dispName = ref("")

const type1 = ref("")
const type2 = ref("")

const pokemonDetails = ref({})
const pokedex = ref({})
const genus = ref("")
const image = ref("")

// passing name as route parameter. Check router/index.js for more details

//filter returns all arrays which match condition after arrow function
onMounted(()=>{
    
    pkmName.value = route.params.name.toLowerCase();

    axios.get(`https://pokeapi.co/api/v2/pokemon/${pkmName.value}`).then(data =>{
        image.value = data.data.sprites.other['official-artwork'].front_default
        pokemonDetails.value = data.data
        type1.value = data.data.types[0].type.name
        if(data.data.types[1] !== undefined){
            type2.value = (data.data.types[1].type.name)
        }
        dispName.value = data.data.name[0].toUpperCase() + data.data.name.slice(1)
    });

    axios.get(`https://pokeapi.co/api/v2/pokemon-species/${pkmName.value}`).then(data =>{
        pokedex.value = data.data.flavor_text_entries[7]
        genus.value = data.data.genera[7].genus
    })

});


</script>


<style lang="scss" scoped>

</style>