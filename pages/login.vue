<template>
<div style="background-color:brown; padding: 1px">
    <h1 style="text-align:center">Log in Page</h1>
</div>

<div class="form-center">
    <input type="email" placeholder="Enter your email" id="email" v-model="state.email"/><br /><br />
    <input type="text" placeholder="Enter your password" id="password" v-model="state.password"/><br /><br />
    <button class="login" type="button" v-on:click="login()">Login</button>
</div>

<div>
    <button class="back" type="button" v-on:click="homePage()">Back</button>
</div>
</template>

<script>
import axios from 'axios';
import {reactive} from 'vue';
import { useRouter } from 'vue-router';
export default{
    name:'loginComp',
    setup(){
        const router = useRouter();
        const state = reactive({
            email:'',
            password:''
        });
        async function login(){
            let emailID = state.email;
            let pword = state.password;
            await axios.get("/api/login/" + emailID)
                .then((res) => {
                    let result = res.data.data;
                    if (result.length > 0) {
                        if ((result[0].user_password == pword) && (res.status == 200)) {
                            localStorage.setItem("user-name", JSON.stringify(result[0].first_name));
                            localStorage.setItem("user-id", JSON.stringify(result[0].user_id));
                            localStorage.setItem("isAdmin", JSON.stringify(result[0].isAdmin));
                            alert('Login Successfull');
                            if(result[0].isAdmin == 'true'){
                                router.push('/admin')
                            }else{
                                router.push('/loggedin/dashboard')
                            }
                        } else {
                            alert("Incorrect password");
                            state.password = '';
                        }
                    } else {
                        alert("Account doesn't exist. Please enter proper details");
                        state.email = ''
                        state.password = '';
                    }
                })
        }
        function homePage(){
            return router.push('/')
        }
        return{
            state,
            homePage,
            login
        }
    }
}

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

.login,
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
    top: 40%;
    left: 46%;
}

.back {
    background-color: rgb(120, 113, 126);
    padding: 10px 22px;
    top: 80%;
    left: 46%;
}
</style>
