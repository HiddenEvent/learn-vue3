<template>
	<div class="container py-4">
		<input ref="input" type="text" />
		<p>{{ input }}</p>
		<p v-if="input">{{ input.value }} , {{ $refs.input.value }} {{ $refs.input === input }}</p>
	</div>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
	setup() {
		const input = ref(null);
		console.log('setup : ', input.value);
		onMounted(() => {
			input.value.value = 'Hellow World';
			console.log('onMounted : ', input.value);
		});
		return { input };
	},
};
</script>

<style scoped></style>
