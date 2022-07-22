<script>
import Button from './Button.vue'
import Image from './ImageS.vue'

export default {
    name: 'Login',
    components: {
        Button,
        Image,
    },
    data() {
        return {
            name: '',
            password: '',
        }
    },
    methods: {
        async handleSubmit() {
            if (!this.name && !this.password) {
                alert('Please enter your Username and Password')
                return
            }
            if (!this.name) {
                alert('Please enter your Username')
                return
            }
            if (!this.password) {
                alert('Please enter your Password')
                return
            }

            // !this.name ? alert('enter your name'): alert('success')


            const data = {
                name: this.name,
                password: this.password
            }
        }
    }

}
</script>

<template>
    <div class="grid md:grid-cols-2 mt-5 items-center login--body">
        <Image />
        <div class="flex flex-col items-center justify-center">
            <h1 class="text-4xl ">Welcome Someone</h1>

            <h2 class="text-3xl font-semibold mb-5">Login Here</h2>

            <form @submit.prevent="handleSubmit" class="flex flex-col gap-5 w-80">
                <input type="text" name="name" v-model="name" id="nameText" placeholder="Enter Your Name Here"
                    class="rounded p-2">
                <input type="password" name="password" v-model="password" id="passwordText"
                    placeholder="Enter Your Password Here" class="rounded p-2">

                <Button text='Login' />
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