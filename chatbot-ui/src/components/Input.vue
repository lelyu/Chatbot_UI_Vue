<script setup>
	import { ref } from 'vue'
	const inputValue = ref('')

	const handleSubmit = () => {
		console.log('User: ', inputValue.value)
		inputValue.value = ''
	}
</script>

<template>
	<form
		@submit.prevent="handleSubmit"
		class="w-full flex flex-row bg-amber-50 gap-1">
		<input
			v-model="inputValue"
			type="text"
			placeholder="Ask AI"
			class="basis-3/4" />
		<button type="submit" class="basis-1/4 bg-amber-600">Send</button>
	</form>
</template>

<style scoped></style>
