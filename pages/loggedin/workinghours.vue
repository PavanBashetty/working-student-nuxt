<template>
<loggedIn subHeaderName="Working hours" />

<!--FILTER DIV-->
<div class="grid mb-2 grid-cols-4">
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <select class="block py-2 w-70 border border-gray-300 bg-white rounded-md shadow-sm sm:text-sm">
        <option value="" disabled selected>Select Company Name</option>
        <option>Bosch</option>
        <option>Benz</option>
        <option>SAP</option>
    </select>
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <input type="number" class="w-full max-w-md block py-2  border border-gray-300 bg-white rounded-md shadow-sm placeholder-black sm:text-sm gap-4" placeholder="Enter a month number" />
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <button class="text-blue-700 font-semibold  py-1 px-4 border border-gray-500 rounded-full" type="button" ref="submit">Apply</button>
        <button class="text-blue-700 font-semibold  py-1 px-4 border border-gray-500 rounded-full">Reset</button>
    </div>
    <div class="bg-gray-150 p-2 grid-auto-cols">
        <p>Total Worked Hours: 12</p>
    </div>
</div>

<!--STATIC TABLE TO DISPLAY WORKED HOURS DETAILS FOR EACH COMPANY-->
<div class="conatiner mx-auto h-64 overflow-y-auto">
    <table class="min-w-full divide-y divide-gray-200">
        <thead class="bg-gray-100 sticky top-0 z-10 text-left">
            <tr>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">User ID</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Company Name</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Worked Date</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Worked Week</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Worked Month</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Hours Worked</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Working Status</th>
            </tr>
        </thead>
        <tbody class="bg-white divide-y divide-gray-200 ">
            <tr>
                <td class="px-1 py-1 text-left whitespace-nowrap">10001</td>
                <td>Bosch</td>
                <td>01.06.2023</td>
                <td>22</td>
                <td>06</td>
                <td>8</td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-300 ">Active</span></td>
            </tr>
            <tr>
                <td class="px-1 py-1 text-left whitespace-nowrap">10001</td>
                <td>Benz</td>
                <td>02.06.2023</td>
                <td>22</td>
                <td>06</td>
                <td>4</td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-300 ">Active</span></td>
            </tr>
        </tbody>
    </table>
</div>

<!--ENTER LATEST WORKED DETAILS-->
<div class="text-center">
    <button class="text-white bg-blue-700 hover:bg-red-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800" v-on:click="showComponent = true">Enter Latest Work Hours</button>
    <button class="text-white bg-blue-700 hover:bg-red-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800" v-show="showComponent" v-on:click="showComponent = false">Close Below Form</button>
</div>

<form v-show="showComponent">
    <div class="grid gap-6 mb-6 md:grid-cols-4">
        <div>
            <label for="userid" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">User ID:</label>
            <input type="text" id="userid" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" value="10001" :disabled="true">
        </div>
        <div>
            <label for="companyName" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Company Name:</label>
            <select id="companyName" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" >
                <option value="" disabled selected>Select the company name</option>
                <option>Bosch</option>
                <option>Benz</option>
                <option>SAP</option>
            </select>
        </div>
        <div>
            <label for="workHours" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Hours Worked:</label>
            <input type="number" id="workHours" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
        </div>
        <div>
            <label for="workDate" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Worked Date:</label>
            <input type="date" id="workDate" min="0" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-1/2 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500">
        </div>
    </div>
    <button type="button" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 font-medium rounded-lg text-sm w-full sm:w-auto px-5 py-2.5 text-center dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">Submit</button>
</form>

</template>

<script>
import loggedIn from '~/layouts/loggedin.vue'
// definePageMeta({
//     layout: 'loggedin'
// })
export default {
    components: {
        loggedIn
    },
    data(){
        return{
            showComponent: false
        }
    }
}
</script>

<style>
</style>
