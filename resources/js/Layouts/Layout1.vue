<script setup>
    import MainNav from '@/Components/MainNav.vue'
    import { ref } from 'vue';

    let width = ref('w-[250px]')
    let hidden = ref("")

    function toggleWidth() {
        if(width.value == 'w-[250px]') {
            width.value = 'w-[50px]'
            hidden.value = "hidden"
        }else {
            width.value = ['w-[250px]']
            hidden.value = ""
        }
    }
</script>

<template>

<div class="flex min-h-screen">
    <div id="sidebar" class="bg-blue-900 p-6 duration-500" :class="width" style="position: relative;">
        <button class="text-xl text-gray-600" @click="toggleWidth" style="position: absolute; right: 10px; top:10px">
            <i class="fa-solid fa-bars text-blue-500"></i>
        </button>
        <div id="branding" :class="hidden">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRUMLiKc8WCsotxfJELuuMgOBODCEa9wiGYvw&usqp=CAU" alt="Logo"
                class="w-[170px] h-[170px] mx-auto rounded-full object-cover">
            <h1 class="text-3xl text-center text-blue-300 my-6">Amazon Smirks</h1>
            <MainNav></MainNav>
        </div>
        <hr class="border-blue-600">

    </div>
    <div id="container" class="flex-1">
        <slot />
    </div>
</div>

</template>
