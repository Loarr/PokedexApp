<template>
    <div class="h-full max-w-screem overflow-x-scroll">
        <!-- Pokemons list page -->
        <PokemonList />
    </div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';

const PokemonList = defineAsyncComponent(() => import('@/components/PokemonList.vue'))
</script>

<style scoped>

</style>