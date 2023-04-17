<template>
<loggedIn subHeaderName="User Details" />

<!--USER BASIC INFO DETAILS-->
<div class="grid grid-cols-4 gap-1" style="grid-auto-rows: minmax(10px, auto); grid-auto-columns: max-content;">
    <div class="userDetailsHeader">User ID:</div>
    <div class="border p-2">10001</div>
    <div class="userDetailsHeader">Full Name:</div>
    <div class="border p-2">Pavankumar Bashetty</div>
    <div class="userDetailsHeader">Age:</div>
    <div class="border p-2">30</div>
    <div class="userDetailsHeader">Email:</div>
    <div class="border p-2">pavankumar.rb25@gmail.com</div>
</div>
<br>

<!--USER'S work related info-->
<div class="grid grid-cols-2 gap-2" style="grid-auto-rows: minmax(10px, auto); grid-auto-columns: max-content;">
    <div class="grid grid-cols-2 gap-1">
        <div class="userDetailsHeader bg-green-400 flex justify-center items-center">Active Companies:</div>
        <div class="border p-2 flex justify-center items-center">2</div>
        <div class="userDetailsHeader bg-red-400 flex justify-center items-center">Inactive Companies:</div>
        <div class="border p-2 flex justify-center items-center">0</div>
    </div>
    <div class="grid grid-cols-2 gap-1">
        <div class="userDetailsHeader bg-green-400">Total Hours Worked [Active]</div>
        <div class="border p-2 flex justify-center items-center bg-green-100">24</div>
        <div class="userDetailsHeader bg-red-400">Total Hours Worked [Inctive]</div>
        <div class="border p-2 flex justify-center items-center bg-red-100">0</div>
        <div class="userDetailsHeader bg-blue-400">Remaining Work Hours:</div>
        <div class="border p-2 flex justify-center items-center bg-blue-100">{{ 960-24 }}</div>
    </div>
</div>

</template>

<script>
import loggedIn from '~/layouts/loggedin.vue'
// definePageMeta({
//     layout: 'loggedin'
// })
export default {
    components: {
        loggedIn
    }
}
</script>

<style>
.userDetailsHeader {
    @apply font-bold border p-2 bg-gray-300 text-gray-700
}
</style>
