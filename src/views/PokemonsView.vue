<template>
    <div class="bg-stone-300 p-4 rounded-md">
        <div class="h-full max-w-screem px-6 overflow-x-scroll">
        <!-- Pokemons list page -->
        <PokemonList v-model:limit="limit"/>
        <span>{{ limit }}</span>
        </div>
        <div class="rounded-full bg-[url('/woodtexture.png')] w-100% h-10"></div>
        <div>
            <button class="border p-4 m-4" @click="limit='151'">Gen 1</button>
            <button class="border p-4 m-4" @click="limit='100&offset=131'">Gen 2</button>
            <button class="border p-4 m-4" @click="limit='135&offset=251'">Gen 3</button>
            <button class="border p-4 m-4" @click="limit='107&offset=386'">Gen 4</button>
            <button class="border p-4 m-4" @click="limit='156&offset=439'">Gen 5</button>
            <button class="border p-4 m-4" @click="limit='72&offset=649'">Gen 6</button>
            <button class="border p-4 m-4" @click="limit='88&offset=721'">Gen 7</button>
            <button class="border p-4 m-4" @click="limit='96&offset=809'">Gen 8</button>
            <button class="border p-4 m-4" @click="limit='103&offset=905'">Gen 9</button>
        </div>
</div>
</template>

<script setup>
import { defineAsyncComponent } from 'vue';
import { ref } from 'vue';

const limit= ref('20')

const PokemonList = defineAsyncComponent(() => import('@/components/PokemonList.vue'))
</script>

<style scoped>

</style>