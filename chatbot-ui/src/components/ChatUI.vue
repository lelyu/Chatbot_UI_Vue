<script setup>
	import { ref } from 'vue'
	import ChatArea from './ChatArea.vue'
</script>

<template>
	<div class="w-2/3 h-2/3 border-2 border-red-400 flex flex-col p-4 gap-4">
		<h1 class="text-xl font-bold shrink-0">Chat UI</h1>

		<ChatArea class="flex-grow" />
	</div>
</template>

<style scoped></style>
