<template>
    <div class="bg-stone-300 p-4 rounded-md">
        <div class="h-full max-w-screem px-6 overflow-x-scroll">
        <!-- Pokemons list page -->
        <PokemonList :limit="limit"/>
        
        </div>
        <div class="rounded-full bg-[url('/woodtexture.png')] w-100% h-10"></div>
        <div>
            <button>Gen 1</button>
            <button>Gen 2</button>
            <button>Gen 3</button>
            <button>Gen 4</button>
            <button>Gen 5</button>
            <button>Gen 6</button>
            <button>Gen 7</button>
            <button>Gen 8</button>
            <button>Gen 9</button>
        </div>
</div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';
import { ref } from 'vue';

const limit= ref('1008')

const PokemonList = defineAsyncComponent(() => import('@/components/PokemonList.vue'))
</script>

<style scoped>

</style>