<script setup>
import { RouterLink } from 'vue-router'
import ShoppingCart from './ShoppingCart.vue';

</script>

<template>
    <div class="sticky md:pt-0 md:pb-3 lg:pt-0 lg:pb-3 px-28 rounded-b shadow-md">
        <div class="flex items-center gap-9">
            <div class="flex items-center">
                <img
                    class="w-[100px] md:w-[280px] lg:w-[280px]"
                    src="@/assets/img/logo.jpg"
                    alt=""
                />
            </div>
            <div class="lg:w-full md:w-full sm:w-full">
                <div
                    class="flex justify-end md:justify-between lg:justify-between items-center pb-5"
                >
                    <p class="text-2xl hidden md:block lg:block">Hijja Indonesia</p>
                    <div class="flex items-center mt-5 md:mt-0 lg:mt-0">
                        <button class="mx-4">
                            <svg
                                class="w-6 h-6 text-gray-800 dark:text-white"
                                aria-hidden="true"
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                fill="none"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke="currentColor"
                                    stroke-linecap="round"
                                    stroke-width="2"
                                    d="m21 21-3.5-3.5M17 10a7 7 0 1 1-14 0 7 7 0 0 1 14 0Z"
                                />
                            </svg>
                        </button>
                        <button class="mx-4">
                            <svg
                                class="w-6 h-6 text-gray-800 dark:text-white"
                                aria-hidden="true"
                                xmlns="http://www.w3.org/2000/svg"
                                width="24"
                                height="24"
                                fill="none"
                                viewBox="0 0 24 24"
                            >
                                <path
                                    stroke="currentColor"
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M5 4h1.5L9 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm-8.5-3h9.25L19 7H7.312"
                                />
                            </svg>
                        </button>
                    </div>
                </div>
                <div class="hidden md:block lg:block">
                    <RouterLink to="/" class="pr-8" :class="{ 'text-orange-500': $route.path === '/' }">Home</RouterLink>
                    <RouterLink to="/product" class="pr-8" :class="{ 'text-orange-500': $route.path === '/product'}">Product</RouterLink>
                    <RouterLink to="/about" class="pr-8" :class="{ 'text-orange-500': $route.path === '/about'}">About</RouterLink>
                    <RouterLink to="/about" class="pr-8">About</RouterLink>
                </div>
            </div>
        </div>
    </div>
    <ShoppingCart :class=hidden></ShoppingCart>

</template>
