<script setup>
import Product from '@/assets/img/logo.jpg'

const closeCart = () => {
    document.getElementById('cart').classList.toggle('hidden')
}
</script>

<template>
    <div
        :id="'cart'"
        :class="'shadow-lg rounded-l-sm bg-white fixed z-50 top-0 right-0 min-h-screen w-1/4 overflow-y-auto'"
        @click="closeCart"
    >
        <div class="flex items-center justify-between pl-4 pr-2 py-2 gap-8 bg-gray-300">
            <h2>Daftar Belanja</h2>
            <button>
                <span
                    class="py-1 px-3 rounded text-white bg-red-500 hover:bg-red-600 transition-all ease-in 3s cursor-pointer"
                    >X</span
                >
            </button>
        </div>
        <div class="flex items-center justify-center py-8">
            <div class="text-sm">
                <p class="text-center text-gray-500">- Shopping Cart Empty -</p>
            </div>
        </div>
        <div class="absolute right-0 px-4">
            <button
                class="flex items-center py-1 px-3 rounded text-white bg-blue-500 hover:bg-blue-600 transition-all ease-in 3s"
            >
                Next
                <svg
                    class="w-5 h-8 text-white dark:text-white"
                    aria-hidden="true"
                    xmlns="http://www.w3.org/2000/svg"
                    width="24"
                    height="24"
                    fill="currentColor"
                    viewBox="0 0 24 24"
                >
                    <path
                        fill-rule="evenodd"
                        d="M4 4a1 1 0 0 1 1-1h1.5a1 1 0 0 1 .979.796L7.939 6H19a1 1 0 0 1 .979 1.204l-1.25 6a1 1 0 0 1-.979.796H9.605l.208 1H17a3 3 0 1 1-2.83 2h-2.34a3 3 0 1 1-4.009-1.76L5.686 5H5a1 1 0 0 1-1-1Z"
                        clip-rule="evenodd"
                    />
                </svg>
            </button>
        </div>
    </div>
</template>
