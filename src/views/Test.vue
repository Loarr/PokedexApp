<template>
    <div class="scrolling-component" ref="scrollComponent">
        <PostComponent v-for="(post, index) in posts" :post="post" :key="index" />
        <h1>{{ posts.name }}</h1>
    </div>
</template>

<script setup>

import { ref, onMounted, onUnmounted } from 'vue';
// import { useElementVisibility} from '@vueuse/core';
import axios from 'axios';
import PostComponent from '@/components/PostComponent.vue'

const target = ref(null)
// const targetIsVisible = useElementVisibility(target)


const getPosts = (limit) => {
    let ret = []

    for (let i = 1; i < limit; i++) {
        axios.get(`https://pokeapi.co/api/v2/pokemon/${i}`).then(data =>{
            ret.push({
                'name': data.data.forms[0].name
            });
        })
    }
    return ret
}

const loadMorePosts =() => {
    let newPosts = getPosts(10)
    console.log(newPosts)
    posts.value.push(...newPosts)
}

onMounted(()=>{
    window.addEventListener("scroll", handleScroll)
})

onUnmounted(()=>{
    window.removeEventListener("scroll", handleScroll)
})

const handleScroll = (e) =>{
    let element = scrollComponent.value
    if (element.getBoundingClientRect().bottom < window.innerHeight) {
        loadMorePosts()
    }
}

const posts = ref(getPosts(21))
console.log(posts.value)
const scrollComponent = ref(null)

</script>