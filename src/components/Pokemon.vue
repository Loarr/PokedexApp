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


defineProps({
    pokemon:{
        type: Object,

    }
})

const types = ["grass", "fire", "water", "normal"]

</script>

<style scoped>
.grass{
    @apply bg-[#7AC74C];
}
.fire{
    @apply bg-[#EE8130];
}

.water{
    @apply bg-[#6390F0];
}

.normal{
    @apply bg-[#A8A77A];
}

.electric{
    @apply bg-[#F7D02C];
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

.default{
    @apply bg-black
}
</style>