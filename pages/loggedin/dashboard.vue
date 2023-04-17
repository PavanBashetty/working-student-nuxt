<template>
    <loggedIn subHeaderName = "Dashboard" />
     Dashboard
    
</template>

<script>
import loggedIn from '~/layouts/loggedin.vue'
// definePageMeta({
//     layout: 'loggedin'
// })
export default{
    components:{
        loggedIn
    }
}
</script>

<style scoped>
</style>