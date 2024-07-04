<script setup>
import Navbar from '@/components/Navbar.vue'
import {
    Dialog,
    DialogContent,
    DialogDescription,
    DialogFooter,
    DialogHeader,
    DialogTitle,
    DialogTrigger
} from '@/components/ui/dialog'
import ProductCard from '@/components/ProductCard.vue';
</script>

<template>
    <Navbar />
    <div class="px-5 py-8">
        <div class="grid grid-cols-3 place-items-center gap-4">
            <ProductCard/>
            <ProductCard/>
            <ProductCard/>
            <ProductCard/>
            <ProductCard/>
            <ProductCard/>
        </div>
    </div>
</template>
