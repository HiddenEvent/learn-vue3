<template>
	<div class="container py-4">
		<input ref="input" type="text" />
		<p>{{ input }}</p>
		<p v-if="input">{{ input.value }} , {{ $refs.input.value }} {{ $refs.input === input }}</p>
	</div>
	<ul>
		<!--		<li v-for="fruit in fruits" :key="fruit" ref="itemRefs">{{ fruit }}</li>-->
		<li v-for="fruit in fruits" :key="fruit" :ref="el => itemRefs.push(el.textContent)">{{ fruit }}</li>
	</ul>
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
			itemRefs.value.forEach(item => console.log('item : ', item));
		});
		const fruits = ref(['사과', '딸기', '포도']);
		const itemRefs = ref([]);
		return { input, fruits, itemRefs };
	},
};
</script>

<style scoped></style>
