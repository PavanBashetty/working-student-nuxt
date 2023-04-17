<template>
<header>
    <nav class="bg-gray-500 border-gray-200 px-4 lg:px-6 py-4.5 text-white p-5">
        <div class="flex flex-wrap justify-between items-center mx-auto max-w-screen-xl">
            <div class="flex items-center">
                <img src="../static/employee_app.jpg" class="mr-1 h-6 sm:h-9 rounded-full" alt="Flowbite Logo" />
                <span class="self-center text-2xl font-bold whitespace-nowrap dark:text-blue">Working Student App</span>
            </div>
            <div class="flex items-center lg:order-1">
                <h1 class="font-serif text-xl font-extralight text-black-600">{{ subHeaderName }}</h1>
            </div>
            <div class="hidden justify-between items-center w-full lg:flex lg:w-auto lg:order-2">
                <ul class="flex flex-col mt-4 font-medium lg:flex-row lg:space-x-4 lg:mt-0">
                    <li><NuxtLink to="/admin/" class="bg-gray-700 hover:bg-gray-600 text-white py-2 px-1 rounded">Home</NuxtLink></li>
                    <li><NuxtLink to="/admin/adminArchivePage" class="bg-gray-700 hover:bg-gray-600 text-white py-2 px-1 rounded">Archived Data</NuxtLink></li>
                    <li><NuxtLink to="/admin/adminDetailsPage" class="bg-gray-700 hover:bg-gray-600 text-white py-2 px-1 rounded">Admin</NuxtLink></li>
                    <li><NuxtLink to="/login" class="bg-gray-700 hover:bg-gray-600 text-white py-2 px-1 rounded">Log Out</NuxtLink></li>
                </ul>
            </div>
        </div>
    </nav>
</header>

    <!--OUTPUT THE PAGE CONTENT-->
    <div>
        <slot />
    </div>
</template>

<script>
    export default{
        props:{
            subHeaderName:{
                type:String,
                required:true
            }
        }
    }
</script>

<style>
</style>