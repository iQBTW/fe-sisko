<script setup>
import Navbar from '@/components/Navbar.vue'
import Autoplay from 'embla-carousel-autoplay'
import {
    Carousel,
    CarouselContent,
    CarouselItem,
    CarouselNext,
    CarouselPrevious
} from '@/components/ui/carousel'
import axios from 'axios'
import { ref } from 'vue'

const loading = ref(false)

const products = ref([])

const plugin = Autoplay({
    delay: 2000,
    stopOnMouseEnter: true,
    stopOnInteraction: false
})

const fetchProducts = async () => {
    loading.value = true
    try {
        const response = await axios.get('https://sistemtoko.com/public/demo/product')
        const data = products.value = response.data.aaData
        console.log("Data: ", data)
    } catch (error) {
        console.log("Error Fetching: ", error)
    } finally {
        loading.value = false
    }
}
fetchProducts()
</script>

<template>
    <Navbar />
    <main>
        <div class="flex justify-center mt-5">
            <Carousel
                class="w-[500px]"
                :plugins="[plugin]"
                @mouseenter="plugin.stop"
                @mouseleave="[plugin.reset(), plugin.play()]"
            >
                <CarouselContent>
                    <CarouselItem v-for="(product, index) in products" :key="index">
                        <div class="w-[200px]">
                            <img class="w-full" :src="product.photo" alt="Product Photos">
                        </div>
                    </CarouselItem>
                </CarouselContent>
                <CarouselPrevious />
                <CarouselNext />
            </Carousel>
        </div>
    </main>
</template>
