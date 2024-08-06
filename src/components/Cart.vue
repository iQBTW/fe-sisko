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
        <div class="flex items-center">
            <div class="w-1/2">
                <img :src="Product" alt="" srcset="" />
            </div>
            <div class="text-sm">
                <p>ini product</p>
                <span>Rp. 699.000</span>
                <p>Berat 350 gr</p>
                <p>Jumlah :</p>
            </div>
        </div>
    </div>
</template>
