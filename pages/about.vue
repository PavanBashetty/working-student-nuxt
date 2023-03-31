<template>
<div>
    <ul>
        <li v-for="user in users" :key="user">
        {{ user }}</li>
    </ul>
</div>
</template>

<script>
import db from '../server/db.js';
import {
    ref
} from 'vue';
export default {
    name: 'aboutComp',
    setup() {
        const users = ref([]);

       async function getData({
            error
        }) {
            try {
                users.value = await db.query('SELECT user_id FROM userCredentials;')
                return {
                    users
                }
            } catch (err) {
                console.error(err)
                error({
                    statusCode: 500,
                    message: 'Failed to fetch users'
                })
            }
        }
        return{
            users,
            getData
        }
    }
}

</script>

<style>
</style>
