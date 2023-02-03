<template>
    <div>
        <!-- Sign up page -->
        <UserForm formType="signup" @submit="newAccount"/>
    </div>
</template>

<script setup>

import UserForm from '../components/UserForm.vue';

function newAccount(user){
  // api request
  console.log(user.password)
}

</script>

