<template>
<adminLoggedIn subHeaderName="Admin Details" />

<div class="grid grid-cols-4 gap-1" style="grid-auto-rows: minmax(10px, auto); grid-auto-columns: max-content;">
    <div class="userDetailsHeader">Admin ID:</div>
    <div class="border p-2">10000</div>
    <div class="userDetailsHeader">Full Name:</div>
    <div class="border p-2">Goku Saiyan</div>
    <div class="userDetailsHeader">Age:</div>
    <div class="border p-2">50</div>
    <div class="userDetailsHeader">Email:</div>
    <div class="border p-2">goku@gmail.com</div>
</div>
<br><br><hr>

<div class="grid grid-cols-2 gap-2" style="grid-auto-rows: minmax(10px, auto); grid-auto-columns: max-content;">
    <div class="grid grid-cols-2 gap-1">
    <div class="userDetailsHeader bg-purple-400 flex justify-center items-center">Total number of students:</div>
        <div class="border p-2 flex justify-center items-center">10</div>
        <div class="userDetailsHeader bg-red-400 flex justify-center items-center">Total universities:</div>
        <div class="border p-2 flex justify-center items-center">4</div>
</div>
</div>

</template>

<script>
import adminLoggedIn from '~/layouts/adminLoggedIn.vue'
export default {
    components: {
        adminLoggedIn
    }
}
</script>

<style scoped>
.userDetailsHeader {
    @apply font-bold border p-2 bg-gray-300 text-gray-700
}
</style>
