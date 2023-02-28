<template>
    <div class="header">
        <h2>Working Student</h2>
        <div class="header-right">
            <NuxtLink to="/loggedin/dashboard">Home</NuxtLink> || 
            <NuxtLink to="/loggedin/workinghours">Enter Working Hrs</NuxtLink> || 
            <NuxtLink to="/loggedin/companydetails">Company Details</NuxtLink> ||
        </div>
    </div>

    <!--OUTPUT THE PAGE CONTENT-->
    <div>
        <slot />
    </div>
</template>
    
    <script>

    </script>
    
    <style>
    .header {
        overflow: hidden;
        background-color:aqua;
        /* padding: 0px 0px; */
    }

    .header-right {
        float: right;
    }
    @media screen and (max-width: 500px) {
        .header a {
            float: none;
            display: block;
            text-align: left;
        }
        .header-right {
            float: none;
        }
    }
    </style>