<template>
    <RouterLink :to="`/pokemons/${pokemon.name}`">
        <div class="flex items-center space-x-6 w-full p-2 border border-gray-200 cursor-pointer rounded-md">
            <div :class="types.indexOf(pokemon.type1) == -1 ? 'default' : pokemon.type1" class="w-3 h-3 rounded-full"></div>
            <div :class="types.indexOf(pokemon.type2) == -1 ? 'default' : pokemon.type2" class="w-3 h-3 rounded-full"></div>
            <span>{{ pokemon.name }}</span>
        </div>
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