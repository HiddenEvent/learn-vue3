<template>
	<div className="container py-4">
		<div class="card">
			<div class="card-header">ProvideInject Component</div>
			<div class="card-body">
				<button @click="count++">count++</button>
				<Child></Child>
			</div>
		</div>
	</div>
</template>

<script>
import Child from './Child.vue';
import { provide, ref } from 'vue';
export default {
	components: {
		Child,
	},
	setup() {
		const staticMessage = 'static message';
		const message = ref('message');
		const count = ref(10);
		provide('static-message', staticMessage);
		provide('message', message);
		provide('count', count);
		return { staticMessage, message, count };
	},
};
</script>

<style scoped></style>
