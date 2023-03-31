<template>
<div style="background-color:brown; padding: 1px">
    <h1 style="text-align:center">Sign Up Page</h1>
</div>

<div class="form-center">

    <input type="text" placeholder="Enter First Name" id="firstName" v-model="state.firstName" /><br /><br />
    <input type="text" placeholder="Enter Last Name" id="lastName" v-model="state.lastName" /><br /><br />
    <input type="number" placeholder="Enter Age" id="age" v-model="state.age" /><br /><br />
    <input type="text" placeholder="Enter University" id="university" v-model="state.university" /><br /><br />
    <input type="email" placeholder="Enter Email ID" id="email" v-model="state.email" /><br /><br />
    <input type="text" placeholder="Enter Password" id="password" v-model="state.password" /><br /><br />
    <button class="submit" type="button" v-on:click="submitData()">Submit</button>
</div>

<div>
    <button class="back" type="button" v-on:click="homePage()">Back</button>
</div>
</template>

<script>
import axios from 'axios'
import {reactive} from 'vue';
import { useRouter } from 'vue-router';
export default{
    name:'signUpPage',
    setup(){
        const router = useRouter();
        const state = reactive({
            firstName:'pavan',
            lastName:'bashetty',
            age:'',
            university:'',
            email:'',
            password:''
        });
        async function submitData(){
            await axios.post("/api/signup",{
                firstName: this.firstName,
                lastName: this.lastName,
                age: this.age,
                university: this.university,
                email: this.email,
                password: this.password
            }).then((res) => {
                if (res.data.msg == "user registered successfully!") {
                    alert("Registration successfull!");
                    router.push('/login')
                } else {
                    alert("Registration did not happen. Please try again!");
                    this.firstName = '',
                        this.lastName = '',
                        this.age = '',
                        this.university = '',
                        this.email = '',
                        this.password = ''
                }
            }).catch(() => {
                alert("Registration failed. Please try after sometime");
                this.firstName = '',
                    this.lastName = '',
                    this.age = '',
                    this.university = '',
                    this.email = '',
                    this.password = ''
            })
        }
        function homePage(){
            return router.push('/')
        }
        return{
            state,
            submitData,
            homePage
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

.submit,
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
    top: 80%;
    left: 46%;
}

.back {
    background-color: rgb(120, 113, 126);
    padding: 10px 22px;
    top: 90%;
    left: 46%;
}
</style>