<template>
    <RouterLink :to="`/pokemons/${pokemon.name}`">
        <div class="flex items-center space-x-6 w-full p-2 border border-gray-200 cursor-pointer rounded-md">
            <img :src="'public/types/'+pokemon.type1+'.png'" alt="?" class="w-14"/>
            <img :src="'public/types/'+pokemon.type2+'.png'" alt="" class="w-14"/>
            <span>{{ pokemon.name }}</span>
        </div>
        <TypeBar/>
    </RouterLink>
</template>

<script setup>
import { RouterLink } from "vue-router";

defineProps({
    pokemon:{
        type: Object,

    }
})

const types = ["normal", "fire", "water", "electric", "grass", "ice", "fighting", "poison", "ground", "flying", "psychic", "bug", "rock", "ghost", "ghost", "dragon", "dark", "steel", "fairy"]

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