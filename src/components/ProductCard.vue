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
        type: Object,
    }
})
</script>
<template>
    <div class="w-[330px]">
        <Card>
            <CardHeader>
                <CardTitle>{{ product.name }}</CardTitle>
                <CardDescription
                    ><p>{{ product.varian }}</p></CardDescription
                >
            </CardHeader>
            <CardContent><img class="w-fit" :src="product.photo" alt="Product Photo"></CardContent>
            <CardFooter>
                <p class="text-xl font-bold pr-2">Rp. {{ product.price }}</p>
                <button class="py-2 px-5 bg-orange-500 rounded">Buy Now</button>
            </CardFooter>
        </Card>
    </div>
</template>
