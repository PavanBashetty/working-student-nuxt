<template>
<adminLoggedIn subHeaderName="Admin Home" />

<!--FILTER-->
<div class="grid mb-2 md:grid-cols-4">
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <h3>Filters: </h3>
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <select class="block py-2 w-40 border border-gray-300 bg-white rounded-md shadow-sm sm:text-sm">
            <option value="" disabled selected>Select an Header</option>
            <option value="user_id">User ID</option>
            <option value="university">University</option>
            <option value="company_name">Company Name</option>
        </select>
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <input type="text" class="w-full max-w-md block py-2  border border-gray-300 bg-white rounded-md shadow-sm placeholder-black sm:text-sm gap-4" placeholder="Enter a value.." />
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <button class="text-blue-700 font-semibold  py-1 px-4 border border-gray-500 rounded-full" type="button">Apply</button>
        <button class="text-blue-700 font-semibold  py-1 px-4 border border-gray-500 rounded-full" type="button">Reset</button>
    </div>
</div>

<!--STATIC TABLE TO DISPLAY-->
<div class="conatiner mx-auto h-64 overflow-y-auto">
    <table class="min-w-full divide-y divide-gray-200">
        <thead class="bg-gray-100 sticky top-0 z-10">
            <tr>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">User ID</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Full Name</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">University</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Company Name</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Type of Work</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Start Date</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Working Status</th>
                <th class="px- py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Working Hours Left</th>
            </tr>
        </thead>
        <tbody class="bg-white divide-y divide-gray-200 ">
            <tr>
                <td class="px-1 py-1 text-left whitespace-nowrap">10002</td>
                <td>Pavan</td>
                <td>SRH</td>
                <td>Bosch</td>
                <td>Internship</td>
                <td>01.06.2023</td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">Active</span></td>
                <td>940</td>
            </tr>
        </tbody>
    </table>
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

<style>
</style>
