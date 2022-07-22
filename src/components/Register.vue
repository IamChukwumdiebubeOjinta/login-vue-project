<script>
import Button from './Button.vue'
import Image from './ImageS.vue'
import axios from 'axios'

export default {
    name: 'Register',
    components: {
        Button,
        Image,
    },
    data() {
        return {
            first_name: '',
            last_name: '',
            email: '',
            password: '',
            confirm_password: '',
        }
    },
    methods: {
        async handleSubmit() {
            if (!this.first_name && !this.last_name || !this.password && !this.confirm_password) {
                alert('Please fill your Username and Password')
                return
            }
            if (!this.first_name) {
                alert('Please fill your First Name')
                return
            }
            if (!this.last_name) {
                alert('Please fill your Last Name')
                return
            }
            if (!this.password) {
                alert('Please fill in your Password')
                return
            }
            if (!this.confirm_password) {
                alert('Please fill in your Password')
                return
            }
            if (!this.email) {
                alert('Please fill in your email address')
                return
            }

            // !this.name ? alert('enter your name'): alert('success')


            const data = {
                firstName: this.first_name,
                lastName: this.last_name,
                email: this.email,
                password: this.password,
                confirmPassword: this.confirm_password,
            }

            axios.post('http://127.0.0.1:3000/Register', data)
                .then(
                    res => {
                        console.log(res);
                    }
                ).catch(
                    err => {
                        console.log(err);
                    }
                )
        }
    }

}
</script>

<template>
    <div class="grid md:grid-cols-2 mt-5 items-center login--body">
        <Image />
        <div class="flex flex-col items-center justify-center">
            <h1 class="text-4xl ">Hello There</h1>

            <h2 class="text-3xl font-semibold mb-5">Register Here</h2>

            <form @submit.prevent="handleSubmit" class="flex flex-col gap-5 w-80">
                <input type="text" name="name" v-model="first_name" id="firstName" placeholder="Enter Your First Name Here"
                    class="rounded p-2">
                <input type="text" name="name" v-model="last_name" id="lastName" placeholder="Enter Your Last Name Here"
                    class="rounded p-2">
                <input type="email" name="name" v-model="email" id="eMail" placeholder="Enter Your email Here"
                    class="rounded p-2">
                <input type="password" name="password" v-model="password" id="password"
                    placeholder="Enter Your Password Here" class="rounded p-2">
                <input type="password" name="password" v-model="confirm_password" id="confirmPassword"
                    placeholder="Confirm Password Here" class="rounded p-2">

                <Button text='Sign Up' />
            </form>
        </div>
    </div>


</template>

<style>
form {
    padding: 5px;
    border-radius: 2px;
    box-shadow: 2px 2px 1px rgba(0, 0, 0, 0.219);
}
</style>