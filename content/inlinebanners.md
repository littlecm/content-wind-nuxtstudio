# Inline Banners

title: "Inline Banners"

description: "A page to display inline banners fetched from an API"

\---

\<script setup>

import { ref, onMounted } from 'vue'

const banners = ref(\[])

const fetchBanners = async () => {

try {

const response = await fetch('https\://hasura-production-e37d.up.railway.app/api/rest/viewinlinebanners')

const data = await response.json()

banners.value = data.inlinebanners

} catch (error) {

console.error('Error fetching banners:', error)

}

}

onMounted(() => {

fetchBanners()

})

\</script>

\<template>

\<div class="container mx-auto p-4">

\<h1 class="text-2xl font-bold mb-4">Inline Banners\</h1>

\<table class="table-auto w-full border-collapse border border-gray-300">

\<thead>

\<tr class="bg-gray-100">

\<th class="border border-gray-300 p-2">Account ID\</th>

\<th class="border border-gray-300 p-2">Desktop Image\</th>

\<th class="border border-gray-300 p-2">Mobile Image\</th>

\<th class="border border-gray-300 p-2">URL\</th>

\</tr>

\</thead>

\<tbody>

\<tr v-for="banner in banners" \:key="banner.id">

\<td class="border border-gray-300 p-2">{{ banner.accountid }}\</td>

\<td class="border border-gray-300 p-2">

\<img \:src="banner.desktopimage" alt="Desktop Image" class="w-32 h-auto">

\</td>

\<td class="border border-gray-300 p-2">

\<img \:src="banner.mobileimage" alt="Mobile Image" class="w-32 h-auto">

\</td>

\<td class="border border-gray-300 p-2">

\<a \:href="banner.url" target="\_blank" class="text-blue-500 underline">{{ banner.url }}\</a>

\</td>

\</tr>

\</tbody>

\</table>

\</div>

\</template>

\<style scoped>

.container {

max-width: 800px;

}

\</style>
