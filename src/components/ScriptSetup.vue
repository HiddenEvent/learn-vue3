<template>
	<div>{{ msg }}</div>
	{{ refMsg }}
	<input v-model="refMsg" type="text" />
	<button @click="sayHello">click</button>
	<PostCreate></PostCreate>
</template>

<script setup>
import { ref } from 'vue';
import PostCreate from './setup/PostCreate.vue';

const msg = 'Hellow world';
const refMsg = ref('');
const sayHello = () => {
	alert('Hello World!');
};
</script>

<style scoped></style>
