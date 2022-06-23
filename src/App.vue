<template>
	<div>
		<h2>반응형 메세지</h2>
		<p>{{ reactiveMessage }}</p>
		<button v-on:click="addReactiveMessage">메세지 추가</button>
		<h2>일반 메세지</h2>
		<p>{{ nomalMessage }}</p>
		<button v-on:click="addNomalMessage">메세지 추가</button>
	</div>
</template>

<script>
import { onBeforeMount, onMounted, ref } from 'vue';

export default {
	setup() {
		console.log('setup 호출');
		const reactiveMessage = ref('난 반응형 메세지 입니다.');
		const addReactiveMessage = () => {
			reactiveMessage.value = reactiveMessage.value + '!';
		};
		// console.log(isRef(reactiveMessage));

		let nomalMessage = '난 기본 메세지 입니다.';
		const addNomalMessage = () => {
			nomalMessage = nomalMessage + '!';
		};
		// console.log(isRef(nomalMessage));

		onMounted(() => {
			console.log('onMounted');
		});
		onBeforeMount(() => {
			console.log('onBeforeMount');
		});

		return {
			reactiveMessage,
			nomalMessage,
			addReactiveMessage,
			addNomalMessage,
		};
	},
};
</script>
