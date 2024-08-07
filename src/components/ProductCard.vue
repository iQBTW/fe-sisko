<script setup>
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle
} from '@/components/ui/card'

defineProps({
    product: {
        type: Object
    }
})
</script>
<template>
    <div class="w-[330px] px-3 py-2">
        <Card>
            <CardHeader>
                <img class="w-fit" :src="product.photo" alt="Product Photo" />
            </CardHeader>
            <CardContent>
                <CardTitle class="text-center">{{ product.name }}</CardTitle>
            </CardContent>
            <CardFooter class="flex justify-between">
                <p class="text-xl font-bold pr-2">Rp. {{ product.price }}</p>
                <button class="py-2 px-5 bg-black text-white rounded">Buy Now</button>
            </CardFooter>
        </Card>
    </div>
</template>
