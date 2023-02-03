<template>
    <form class="flex flex-col mt-10 space-y-7" @submit.prevent="submitForm">
        <div class="form-group" v-if="formType == 'signup'">
            <label class="label" for="fullname">Full name</label>
            <input class="input" type="text" name="fullname" v-model="user.fullname" id=""/>
        </div>
        <div class="form-group">
            <label class="label" for="email">Email</label>
            <input class="input" type="text" name="email" v-model="user.email" id=""/>
        </div>
        <div class="form-group">
            <label class="label" for="password">Password</label>
            <input class="input" type="password" name="password" v-model="user.password" id=""/>
        </div>
        <button class="button">{{ formType == 'signup' ? 'Sign Up' : 'Sign In' }}</button>
    </form>
    <!-- Add links for sign up, sign in, forgotten password, which only display when showing correct form type -->
</template>

<script setup>

    import { reactive } from 'vue';

    defineProps({
        formType:{
            type: String,
            default: "signup"
        }
    })

    const emit = defineEmits(["submit"])

    function submitForm(){
        emit("submit", user)
    }

    const user = reactive({
        fullname: "",
        email: "",
        password: "",
    })

</script>

<style scoped>

    .input{
        @apply border border-gray-200 p-2 rounded-md w-full;
    }

    .label{
        @apply text-lg text-gray-700 font-semibold;
    }

    .button{
        @apply bg-purple-500 text-gray-50 px-4 py-2 rounded;
    }

    .form-gourp{
        @apply flex flex-col space-y-4;
    }

</style>