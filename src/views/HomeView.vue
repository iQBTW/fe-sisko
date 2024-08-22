<script setup>
import ImageCarousel1 from '@/assets/img/nVHxmb_slide1.jpg'
import ImageCarousel2 from '@/assets/img/mGMfXL_slide2.jpg'
import ImageCarousel3 from '@/assets/img/F3na1Q_slide3.jpg'
import Banner1 from '@/assets/img/u8DEdD_banner1.jpg'
import Banner2 from '@/assets/img/bsHxJs_banner2.jpg'
import Banner3 from '@/assets/img/88jcpq_banner3.jpg'
import Navbar from '@/components/Navbar.vue'
import Autoplay from 'embla-carousel-autoplay'
import {
    Carousel,
    CarouselContent,
    CarouselItem,
    CarouselNext,
    CarouselPrevious
} from '@/components/ui/carousel'
import ProductCard from '@/components/ProductCard.vue'
import Footer from '@/components/Footer.vue'
import axios from 'axios'
import { ref } from 'vue'

const loading = ref(false)

const products = ref([])

const imgCarousel = [
    {
        images: ImageCarousel1
    },
    {
        images: ImageCarousel2
    },
    {
        images: ImageCarousel3
    }
]

const imgBanner = [
    {
        images: Banner1
    },
    {
        images: Banner2
    },
    {
        images: Banner3
    },
]

const plugin = Autoplay({
    delay: 2000,
    stopOnMouseEnter: true,
    stopOnInteraction: false
})

const fetchProducts = async () => {
    loading.value = true
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
        <div class="w-full">
            <Carousel
                :plugins="[plugin]"
                @mouseenter="plugin.stop"
                @mouseleave="[plugin.reset(), plugin.play()]"
            >
                <CarouselContent>
                    <CarouselItem v-for="(img, index) in imgCarousel" :key="index">
                        <img class="object-fill w-full" :src="img.images" alt="Carousel Photos" />
                    </CarouselItem>
                </CarouselContent>
                <CarouselPrevious
                    :class="'absolute top-1/2 left-5 z-10 -translate-y-1/2 cursor-pointer'"
                />
                <CarouselNext
                    :class="'absolute top-1/2 right-5 z-10 -translate-y-1/2 cursor-pointer'"
                />
            </Carousel>
        </div>

        <div class="px-8 py-10">
            <div class="flex justify-center items-center gap-10">
                <div class="hover:bg-blend-multiply hover:brightness-50 transition-all duration-300 delay-500 ease in out" v-for="img, index in imgBanner" :key="index">
                    <img class="w-[380px] hover:scale-105 transition-transform duration-300 transform" :src="img.images" alt="Banner">
                </div>
            </div>
        </div>

        <div class="px-8 py-10">
            <div class="grid grid-cols-4 place-items-center gap-4">
                <ProductCard v-for="product in products" :key="product.id" :product="product" />
            </div>
        </div>
    </main>
    <Footer />
</template>
