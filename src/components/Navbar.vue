<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div class="sticky py-5 px-16 rounded-b shadow-md">
        <div class="flex items-center gap-9">
            <div class="">
                <img class="w-[60px]" src="../assets/logo.svg" alt="">
            </div>
            <div class="flex gap-3">
                <RouterLink to="/">Home</RouterLink>
                <RouterLink to="/product">Product</RouterLink>
                <RouterLink to="/about">About</RouterLink>
            </div>
        </div>
    </div>
</template>