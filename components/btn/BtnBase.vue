<template>
	<button
		@click="loading"
		class="transition-colors duration-500 border-[1px] border-black hover:border-blue-400 hover:bg-blue-400 hover:text-white">
		<p v-if="isLoading"><slot>текст кнопки</slot></p>
		<div v-else>Loading...</div>
	</button>
</template>

<script setup lang="ts">
let isLoading = ref<boolean>(true);

console.log(isLoading);

function loading() {
	setTimeout(() => {
		setTimeout(() => {
			isLoading.value = !isLoading.value;
		}, 2000);
		isLoading.value = !isLoading.value;
	}, 1000);
}
</script>

<style scoped lang="scss"></style>
