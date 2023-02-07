<template>
    <RouterLink :to="`/pokemons/${pokemon.name}`">
        <div class="flex flex-col items-center w-20 h-96 p-2 border bg-yellow-800 border-gray-200 cursor-pointer rounded-md">
            <img :src="'/types/'+type1+'.png'" alt="" class="w-14 h-14 mb-4"/>
            <img :src="'/types/'+type2+'.png'" alt="" class="h-14 mb-4"/>
            <div class="rotate-90 h-10 text-center my-8">
                <span class="font-semibold">{{ pkmName }}</span>
            </div>
            <div class="border-t-2 border-black font-semibold text-center mt-8 w-14">
                <span>{{ pokemonDetails.id < 10 ? '00'+pokemonDetails.id : '0'+pokemonDetails.id }}</span>
            </div>
            <div>
                <img :src="sprite"/>
            </div>
        </div>

    </RouterLink>
</template>

<script setup>
import { RouterLink } from "vue-router";
import axios from 'axios';
import { onMounted, ref } from 'vue';

const prop = defineProps(['pokemon'])

const url = prop.pokemon.url
const pokemonDetails = ref({})
const type1 = ref("")
const type2 = ref("")
const sprite = ref("")
const pkmName = prop.pokemon.name[0].toUpperCase()+prop.pokemon.name.slice(1)

onMounted(()=>{
    axios.get(url).then(data =>{
        pokemonDetails.value= data.data
        type1.value = (pokemonDetails._rawValue.types[0].type.name)
        if(pokemonDetails._rawValue.types[1] !== undefined){
            type2.value = (pokemonDetails._rawValue.types[1].type.name)
        }
        sprite.value = pokemonDetails._rawValue.sprites.front_default
    })
})


</script>

<style scoped>
.normal{
    @apply bg-[#A8A77A];
}

.fire{
    @apply bg-[#EE8130];
}

.water{
    @apply bg-[#6390F0];
}


.electric{
    @apply bg-[#F7D02C];
}

.grass{
    @apply bg-[#7AC74C];
}
.ice{
    @apply bg-[#96D9D6];
}

.fighting{
    @apply bg-[#C22E28];
}

.poison{
    @apply bg-[#A33EA1];
}

.ground{
    @apply bg-[#E2BF65];
}

.flying{
    @apply bg-[#A98FF3];
}

.psychic{
    @apply bg-[#F95587];
}

.bug{
    @apply bg-[#A6B91A];
}

.rock{
    @apply bg-[#B6A136];
}

.ghost{
    @apply bg-[#735797];
}

.dragon{
    @apply bg-[#6F35FC];
}

.dark{
   @apply bg-[#705746]; 
}

.steel{
    @apply bg-[#B7B7CE];
}

.fairy{
    @apply bg-[#D685AD];
}

.default{
    @apply bg-white
}
</style>