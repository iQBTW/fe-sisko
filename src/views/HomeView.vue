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

const plugin = Autoplay({
    delay: 2000,
    stopOnMouseEnter: true,
    stopOnInteraction: false
})
</script>

<template>
    <Navbar />
    <main>
        <div class="flex justify-center mt-5">
            <Carousel
                class="relative w-full max-w-xs"
                :plugins="[plugin]"
                @mouseenter="plugin.stop"
                @mouseleave="[plugin.reset(), plugin.play()]"
            >
                <CarouselContent>
                    <CarouselItem v-for="(_, index) in 5" :key="index">
                        <div class="w-[200px]">
                            {{ index + 1 }}
                        </div>
                    </CarouselItem>
                </CarouselContent>
                <CarouselPrevious />
                <CarouselNext />
            </Carousel>
        </div>
    </main>
</template>
