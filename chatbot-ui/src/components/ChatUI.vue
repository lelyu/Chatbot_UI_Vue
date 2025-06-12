<script setup>
	import { ref } from 'vue'
	import ChatArea from './ChatArea.vue'
	import Input from './Input.vue'
</script>

<template>
	<div class="w-full h-full border-2 border-red-400 flex flex-col p-4 gap-4">
		<h1 class="text-xl font-bold shrink-0">Chat UI</h1>
		<ChatArea />
		<Input />
	</div>
</template>

<style scoped></style>
