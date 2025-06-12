<script setup>
	import { ref } from 'vue'
	import Input from './Input.vue'
	import mockData from '../assets/mockData.json'
	import mockResponse from '../assets/mockResponse.json'

	const chatHistory = ref([])
	const userInput = ref('')

	const handleMessageSubmit = () => {
		chatHistory.value.push(userInput.value)
		console.log('current chat history', chatHistory.value)
		userInput.value = ''
	}
</script>

<template>
	<div class="w-full h-full border-4 border-amber-400 p-2 flex flex-col">
		<div
			v-if="chatHistory.length === 0"
			class="flex justify-center items-center">
			<p class="text-2xl">Hello. Let's start chatting!</p>
		</div>
		<div v-else class="flex"></div>
		<Input
			class="mt-auto"
			v-model="userInput"
			@submit="handleMessageSubmit" />
	</div>
</template>

<style scoped></style>
