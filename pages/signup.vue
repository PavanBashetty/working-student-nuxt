<template>
<div style="background-color:brown; padding: 1px">
    <h1 style="text-align:center">Sign Up Page</h1>
</div>

<div class="form-center">

    <input type="text" placeholder="Enter First Name" id="firstName" v-model="firstName" /><br /><br />
    <input type="text" placeholder="Enter Last Name" id="lastName" v-model="lastName" /><br /><br />
    <input type="number" placeholder="Enter Age" id="age" v-model="age" /><br /><br />
    <input type="text" placeholder="Enter University" id="university" v-model="university" /><br /><br />
    <input type="email" placeholder="Enter Email ID" id="email" v-model="email" /><br /><br />
    <input type="text" placeholder="Enter Password" id="password" v-model="password" /><br /><br />
    <button class="submit" type="button" v-on:click="submitData()">Submit</button>
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

.submit,
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
    top: 80%;
    left: 46%;
}

.back {
    background-color: rgb(120, 113, 126);
    padding: 10px 22px;
    top: 90%;
    left: 46%;
}
</style>