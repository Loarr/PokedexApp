<template>
    <div>
        <div class="h-screen">
            <p>{{ targetIsVisible }}</p>
        </div>
        <div ref="target">
            <h1>Hello world</h1>
            <P>{{ targetIsVisible }}</P>
        </div>
    </div>
</template>

<script setup>

import { ref } from 'vue'
import { useElementVisibility } from '@vueuse/core'

const target = ref(null)
const targetIsVisible = useElementVisibility(target)

</script>

<style lang="scss" scoped>

</style>