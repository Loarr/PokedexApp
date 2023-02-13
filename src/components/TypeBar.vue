<template>
    <div class="flex bg-[#9FA19F] text-white w-28 font-semibold">
        <img :src="'/types/'+props.pkmType+'.png'" class="w-8"/><p class="text-center m-auto">{{ type }}</p>
    </div>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps({
    pkmType:{
        type: String
    }
})

const type = computed(()=>{
    return props.pkmType[0]?.toUpperCase() + props.pkmType.slice(1)
})


</script>

