<template>
	<div></div>
</template>

<script>
import { ref, watch } from 'vue';

export default {
	setup() {
		const x = ref(0);
		const y = ref(0);

		// single ref
		watch(x, newX => {
			console.log(`x 는 ${newX}`);
		});

		// getter
		watch(
			() => x.value + y.value,
			sum => {
				console.log(`x + y : ${sum}`);
			},
		);

		// array of multiple sources
		watch([x, y], ([newX, newY]) => {
			console.log(`x is ${newX} and y is ${newY}`);
		});
		return { x, y };
	},
};
</script>
