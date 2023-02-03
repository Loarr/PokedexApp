<template>
    <div class="flex items-center space-x-6">
        <div :class="types.indexOf(pokemon.type1) == -1 ? 'default' : pokemon.type1" class="w-3 h-3 rounded-full"></div>
        <span>{{ pokemon.name }}</span>
    </div>
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