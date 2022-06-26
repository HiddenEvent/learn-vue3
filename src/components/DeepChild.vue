<template>
	<div class="card">
		<div class="card-header">Deep Child Component</div>
		<div class="card-body">
			<p>{{ staticMessage }}</p>
			<p>{{ message }}</p>
			<p>{{ count }}</p>
		</div>
	</div>
</template>

<script>
import { inject } from 'vue';

export default {
	setup() {
		const staticMessage = inject('static-message', '값이 없으면 디폴트');
		const message = inject('message');
		const count = inject('count');
		return { staticMessage, message, count };
	},
};
</script>

<style scoped></style>
