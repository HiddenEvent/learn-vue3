<template>
	<div class="card">
		<div class="card-body">Lifecycle Child</div>
		<input id="input" type="text" />
	</div>
</template>

<script>
import { onBeforeMount, onBeforeUnmount, onMounted, onUnmounted } from 'vue';

export default {
	setup() {
		// console.log('[Child] setup');
		// onBeforeMount(() => {
		// 	console.log('[Child] onBeforeMount');
		// });
		// onMounted(() => {
		// 	console.log('[Child] onMounted');
		// });
		onBeforeUnmount(() => {
			console.log('onBeforeUnmount : ');
			console.log(document.querySelector('#input'));
		});
		onUnmounted(() => {
			console.log('onUnmounted : ');
			console.log(document.querySelector('#input'));
		});
		return {};
	},
};
</script>

<style scoped></style>
