<template>
    <div class="bg-stone-300 p-4 rounded-md">
        <div class="h-full max-w-screem px-6 overflow-x-scroll">
        <!-- Pokemons list page -->
        <PokemonList />
        
        </div>
        <div class="rounded-full bg-[url('/woodtexture.png')] w-100% h-10"></div>
</div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';

const PokemonList = defineAsyncComponent(() => import('@/components/PokemonList.vue'))
</script>

<style scoped>

</style>