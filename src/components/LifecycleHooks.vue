<template>
	<div class="container py-4">
		<input ref="inputRef" type="text" value="hellow world" />
		<!--		<LifecycleChild></LifecycleChild>-->
		<p id="message">{{ message }}</p>
	</div>
</template>

<script>
import { onBeforeMount, onBeforeUpdate, onMounted, onUpdated, ref } from 'vue';
// import LifecycleChild from './LifecycleChild.vue';

export default {
	components: {
		// LifecycleChild,
	},
	setup() {
		// console.log('setup');
		const inputRef = ref(null);
		const message = ref('');
		// onBeforeMount(() => {
		// 	console.log('onBeforeMount', inputRef.value); /*Dom 데이터를 읽어 올 수 없음*/
		// });
		// onMounted(() => {
		// 	console.log('onMounted', inputRef.value.value); /*Dom 데이터를 읽어온다.*/
		// });
		onBeforeUpdate(() => {
			console.log('onBeforeUpdate :', message.value);
			console.log('DoOM Content: ', document.querySelector('#message').textContent);
		});
		onUpdated(() => {
			console.log('onUpdated : ', message.value);
			console.log('DoOM Content: ', document.querySelector('#message').textContent);
		});
		return { inputRef, message };
	},
	// data: () => ({
	// 	dataMessage: 'dataMessage',
	// }),
	// beforeCreate() {
	// 	console.log('beforeCreate : ', this.dataMessage); /*data 접근할 수 없음*/
	// },
	// created() {
	// 	console.log('created : ', this.dataMessage); /*data 접근 가능*/
	// },
};
</script>

<style scoped></style>
