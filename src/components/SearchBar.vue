<script setup>
const closeSearch = () => {
    document.getElementById('searchbar').classList.toggle('hidden')
}
</script>

<template>
    <div :id="'searchbar'" class="h-screen fixed w-full z-50 bg-black/75 top-0">
        <div class="absolute right-0 top-0 py-6 px-3">
            <button @click="closeSearch">
                <span class="py-3 px-5 text-white text-lg bg-blue-500 hover:bg-blue-600 transition-all ease-in 3s cursor-pointer">X</span>
            </button>
        </div>
        <div class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2">
            <input type="text" placeholder="Type here" class="w-[1100px] outline-none bg-white/0 text-3xl text-white placeholder:text-white text-center">
            <hr class="w-full mt-2 bg-white">
        </div>
        <div class="absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 pt-44">
            <button class="py-2 px-3 rounded text-white text-sm bg-blue-500 hover:bg-blue-600 transition-all ease-in 3s cursor-pointer">
                Search
            </button>
        </div>
    </div>
</template>