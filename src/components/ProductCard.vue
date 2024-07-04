<script setup>
import {
    Card,
    CardContent,
    CardDescription,
    CardFooter,
    CardHeader,
    CardTitle
} from '@/components/ui/card'
</script>
<template>
    <div class="w-[330px]">
        <Card>
            <CardHeader>
                <CardTitle>Title</CardTitle>
                <CardDescription
                    >Lorem ipsum dolor sit amet consectetur, adipisicing elit. Optio eius dolores
                    officiis eos tenetur id.</CardDescription
                >
            </CardHeader>
            <CardContent>Content</CardContent>
            <CardFooter>
                <button class="py-2 px-5 bg-orange-500 rounded">Buy Now</button>
            </CardFooter>
        </Card>
    </div>
</template>
