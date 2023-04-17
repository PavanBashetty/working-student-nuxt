<template>
<div class="text-center" style="background-color:brown; padding: 30px">
    <h1 class="self-center text-2xl font-bold whitespace-nowrap dark:text-blue">Welcome to Working Student App</h1>
</div>

<div class="flex h-screen items-center justify-center">
    <!-- <button class="signup" type="button">SignUp</button><br /><br /> -->
    <!-- <button class="login" v-on:click="loginPage()" type="button">Login</button><br /><br /> -->
    
    <NuxtLink to="/signup" class="text-white bg-gradient-to-r from-cyan-500 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-cyan-300 dark:focus:ring-cyan-800 font-medium rounded-lg text-lg px-5 py-2.5 text-center mr-1 mb-1">SignUp</NuxtLink>
    <NuxtLink to="/login" class="text-white bg-gradient-to-r from-cyan-500 to-blue-500 hover:bg-gradient-to-bl focus:ring-4 focus:outline-none focus:ring-cyan-300 dark:focus:ring-cyan-800 font-medium rounded-lg text-lg px-5 py-2.5 text-center mr-1 mb-1">Login</NuxtLink>
 
    <!-- <NuxtLink to="/login">Login</NuxtLink> -->
</div>

<footer>
    <!-- <button type="button">AboutUs</button> -->
    <NuxtLink to="/about" >AboutUs</NuxtLink>
</footer>
</template>

<script setup>

</script>

<style scoped>
footer {
    text-align: center;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0;
    padding: 10px;
    background-color: DarkSalmon;
    color: white;
}
</style>
