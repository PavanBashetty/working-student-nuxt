<template>
<loggedIn subHeaderName="Company Details" />

<!--STATIC TABLE TO DISPLAY ACTIVE COMPANY DETAILS-->
<div class="conatiner mx-auto h-64 overflow-y-auto">
    <table class="min-w-full divide-y divide-gray-200">
        <thead class="bg-gray-100 sticky top-0 z-10 text-left">
            <tr>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">User ID</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Company Name</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Type of Work</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Start Date</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">End Date</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Working Status</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">Total Worked Hours</th>
                <th class="px-1 py-3 text-left text-xs font-medium text-blue-500 uppercase tracking-wider">No longer Work here?</th>
            </tr>
        </thead>
        <tbody class="bg-white divide-y divide-gray-200 ">
            <tr>
                <td class="px-1 py-1 text-left whitespace-nowrap">10001</td>
                <td>Bosch</td>
                <td>Internship</td>
                <td>01.06.2023</td>
                <td><input type="date" :disabled=buttonEnable class="bg-gray-100"/></td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"></span>Active</td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">20</span></td>
                <td><button class="focus:outline-none text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-small rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900" type="button" v-on:click="buttonEnable = !buttonEnable">Enter End Date</button></td>
            </tr>
            <tr>
                <td class="px-1 py-1 text-left whitespace-nowrap">10001</td>
                <td>Benz</td>
                <td>Working Student</td>
                <td>01.07.2023</td>
                <td><input type="date" :disabled=buttonEnable class="bg-gray-100"/></td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800"></span>Active</td>
                <td><span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">10</span></td>
                <td><button class="focus:outline-none text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-small rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900" type="button" v-on:click="buttonEnable = !buttonEnable">Enter End Date</button></td>
            </tr>
        </tbody>
    </table>
</div>
<br /><hr />

<!--ENTER A NEW COMPANY DETAIL-->
<div class="text-center">
    <button class="text-white bg-blue-700 hover:bg-red-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800" v-on:click="showComponent = true">Enter new company details</button>
    <button class="text-white bg-blue-700 hover:bg-red-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800" v-show="showComponent" v-on:click="showComponent = false">Close below form</button>
</div>

<form v-show="showComponent">
    <div class="grid gap-6 mb-6 md:grid-cols-3">
        <div>
            <label for="userid" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">User ID:</label>
            <input type="text" id="userid" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" :disabled="true" value="10001">
        </div>
        <div>
            <label for="companyName" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Company Name:</label>
            <input type="text" id="companyName" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Enter Company Name">
        </div>
        <div>
            <label for="startDate" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Start Date:</label>
            <input type="date" id="startDate" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-1/2 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" required>
        </div>
        <div>
            <label for="grossSalary" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Gross Salary<i>(per hr)</i>:</label>
            <input type="number" id="grossSalary" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" placeholder="Enter Hourly Salary" required>
        </div>
        <div>
            <label for="typeOfWork" class="block mb-2 text-sm font-medium text-gray-900 dark:text-white">Type of Work:</label>
            <select class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500" id="typeOfWork">
                <option value="" disabled selected>Select the work type</option>
                <option value="Working Student">Working Student</option>
                <option value="Part Time">Part Time</option>
                <option value="Internship">Internship</option>
            </select>
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
            buttonEnable: true,
            showComponent: false
        }
    }
}
</script>

<style>
</style>
