<script setup>
import Navbar from '@/components/Navbar.vue'
import ProductCard from '@/components/ProductCard.vue'
import { ref } from 'vue'
import axios from 'axios'

const loading = ref(false)

const products = ref([])

const fetchProducts = async () => {
    // loading.value = true
    try {
        const response = await axios.get('https://sistemtoko.com/public/demo/product')
        const data = (products.value = response.data.aaData)
        console.log('Data: ', data)
    } catch (error) {
        console.log('Error Fetching: ', error)
    } finally {
        loading.value = false
    }
}
fetchProducts()
</script>

<template>
    <Navbar />
    <main>
        <div class="px-5 py-8">
            <div class="grid grid-cols-3 place-items-center">
                <ProductCard
                    v-for="product in products"
                    :key="product.id"
                    :product="product"
                ></ProductCard>
            </div>
        </div>
    </main>
</template>
