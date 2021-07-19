<template>
    <div>
        <form action="javascript:void(0)">
            <input type="text" name="email" placeholder="email" v-model="email"/>
            <input 
                type="password" 
                name="password" 
                placeholder="password" 
                v-model="password"
            />
            <br>
            <input type="submit" value="Login" @click="login()"/>
        </form>
        <h3>{{ status }}</h3>
    </div>
</template>

<script>
import axios from 'axios'
import cookies from 'vue-cookies'

    export default {
        data() {
            return {
                email: undefined,
                password: undefined,
                status: undefined
            }
        },
        methods: {
            login() {
                this.status = "Loading"
                axios
                    .request({
                    url:"https://reqres.in/api/login",
                    method: "POST",
                    data: {
                        email: this.email,
                        password: this.password
                    },
                    headers: {
                        "Content-Type": "application/json",
                    },
                })
                .then((response) => {
                    console.log(response);
                    this.status = "Logged In";
                    //response.data.toke found in devtools once logged in
                    cookies.set("loginToken", response.data.token);
                    this.$router.push("/game");
                })
                .catch((error) => {
                    console.log(error)
                    this.status = "Login Error"
                });
            },
        },
    }
</script>

<style scoped>

</style>