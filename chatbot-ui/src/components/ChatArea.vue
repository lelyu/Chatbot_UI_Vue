<script setup>
	import { ref } from 'vue'
	import Input from './Input.vue'
	import mockData from '../assets/mockData.json'
	import mockResponse from '../assets/mockResponse.json'

	const chatHistory = ref([])
	const userInput = ref('')

	const generateRandomResponse = () => {
		const randomIndex = Math.floor(Math.random() * mockResponse.length)
		return mockResponse[randomIndex]
	}

	const randomRes = ref(generateRandomResponse())

	const handleMessageSubmit = () => {
		chatHistory.value.push({ role: 'user', value: userInput.value })
		userInput.value = ''
		randomRes.value = generateRandomResponse()
		chatHistory.value.push(randomRes.value)
		console.log('current chat history', chatHistory.value)
	}
</script>

<template>
	<div class="w-full h-full border-4 border-amber-400 p-2 flex flex-col">
		<div
			v-if="chatHistory.length === 0"
			class="flex justify-center items-center">
			<p class="text-2xl">Hello. Let's start chatting!</p>
		</div>
		<div v-else class="flex flex-col">
			<div v-for="chat in chatHistory">
				<p class="border-2 border-amber-300">
					{{ chat.role }}: {{ chat.value }}
				</p>
			</div>
		</div>
		<Input
			class="mt-auto"
			v-model="userInput"
			@submit="handleMessageSubmit" />
	</div>
</template>

<style scoped></style>
