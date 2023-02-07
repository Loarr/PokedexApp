<template>
    <div class="flex bg-[#9FA19F] text-white w-28 font-semibold">
        <img :src="'/types/'+pkmType+'.png'" class="w-8"/><p class="text-center m-auto">{{ pkmType }}</p>
    </div>
</template>

<script setup>

defineProps({
    pkmType:{
        type: String
    }
})

function capitalizedFirst(string){
    const capital = string[0].toUpperCase()
    const rest = string.slice(1)
    return captal + rest
}

</script>

<style lang="scss" scoped>

</style>