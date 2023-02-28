<template>
<div style="background-color:brown; padding: 1px">
    <h1 style="text-align:center">Log in Page</h1>
</div>

<div class="form-center">
    <input type="email" placeholder="Enter your email" id="email" /><br /><br />
    <input type="text" placeholder="Enter your password" id="password" /><br /><br />
    <button class="login" type="button" v-on:click="login()">Login</button>
</div>

<div>
    <button class="back" type="button" v-on:click="homePage()">Back</button>
</div>
</template>

<script setup>

</script>

<style scoped>
.form-center {
    text-align: center;
    font-size: large;
    padding-top: 40px;
}

input {
    width: 20%;
    padding: 12px 20px;
    border: 1px solid #ccc;
}

.login,
.back {
    background-color: bisque;
    border: 1px;
    color: black;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    position: absolute;
    top: 40%;
    left: 46%;
}

.back {
    background-color: rgb(120, 113, 126);
    padding: 10px 22px;
    top: 80%;
    left: 46%;
}
</style>
