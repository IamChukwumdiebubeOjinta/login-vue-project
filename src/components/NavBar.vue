<script>
import Button from './Button.vue';
    export default{
    name: "NavBar",
    components: { Button }
}
</script>

<template>
    <div class="flex container mx-auto p-2 justify-between items-center w-full">
        <!-- I used the vue logo -->
        <img src="../assets/vue.svg" alt="logo">

        <div class="flex space-x-2">
            <a href="#" class="p-1 se">🙂</a>
            <Button text="Sign In" class="btn-green" />
            <Button text="Sign Out" class="btn-red" />
        </div>
    </div>
</template>

<style>
    .btn-green:hover{
        background: green;
    }
    .btn-red:hover{
        background: red;
    }
</style>