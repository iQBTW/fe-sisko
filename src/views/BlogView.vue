<script setup>
import Navbar from '@/components/Navbar.vue'
import Image from '@/assets/img/logo.jpg'
import { ref } from 'vue';
import axios from 'axios';

const loading = ref(false)

const gallery = ref([])

const fetchGallery = async () => {
	// loading.value = true
	try {
		const response = await axios.get('https://demo.sistemtoko.com/demo/gallery')
        const data = (gallery.value = response.data.data)
        console.log('Data: ', data)
	} catch (e) {
		console.log('Error Fetching: ', e);
	} finally {
		loading.value = false
	}
}
fetchGallery()
</script>

<template>
	<Navbar />
	
	<main>
		<div class="px-24 py-8">
			<div class="grid grid-cols-3 place-items-center gap-4">
				<div class="w-[500px]" v-for="image in gallery" :key="image.id">
					<img :src=image.url alt="">
					<h2 class="text-center font-bold text-lg pt-3">Hijja Indonesia</h2>
				</div>
			</div>
		</div>
	</main>
</template>