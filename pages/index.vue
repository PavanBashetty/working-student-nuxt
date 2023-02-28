<template>
<div style="background-color:brown; padding: 10px">
    <h1 style="text-align:center">Welcome to Working Student App</h1>
</div>

<div>
    <button class="signup" type="button">SignUp</button><br /><br />
    <button class="login" v-on:click="loginPage()" type="button">Login</button><br /><br />
</div>

<footer>
    <button type="button">AboutUs</button>
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
.signup, .login{
    background-color:bisque;
    border:1px;
    color: black;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    position: absolute;
    top: 25%;
    left: 46%;
}
.login{
    top: 35%;
    left: 46%;
}
</style>
