<script>
    export default{
        name: 'Button',
        props: {
            text: String,
            color: String,
            //class: String,
        },
        
    }
</script>

<template>
    <button type="submit" style="{background: color}" class=" cursor-pointer outline rounded-md outline-slate-600 p-2 hover:bg-black hover:text-white transition ease-in duration-150">{{text}}</button>
</template>