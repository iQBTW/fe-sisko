<script setup>
import { RouterLink } from 'vue-router';
</script>

<template>
    <div class="flex items-baseline justify-between py-5 px-16 bg-slate-500">
        <div class="">
            <img src="../assets/logo.svg" alt="">
        </div>
        <div class="">
            <RouterLink to="/">Home</RouterLink>
            <RouterLink to="/product">Product</RouterLink>
            <RouterLink to="/about">About</RouterLink>
        </div>
        <div class="text">
            <h2>Cart</h2>
        </div>
    </div>
</template>