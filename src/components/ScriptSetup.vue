<template>
	<div>{{ msg }}</div>
	{{ refMsg }}
	<input v-model="refMsg" type="text" />
	<button @click="sayHello">click</button>
	<PostCreate></PostCreate>
</template>

<script setup>
import { ref } from 'vue';
import axios from 'axios';
import PostCreate from './setup/PostCreate.vue';

const msg = 'Hellow world';
const refMsg = ref('');
const sayHello = () => {
	alert('Hello World!');
};
const response = await axios('https://dummy.restapiexample.com/api/v1/employees');
// eslint-disable-next-line no-debugger
debugger;
console.log('response : ', response);
// async function callAPi() {
// 	const response = await axios('https://dummy.restapiexample.com/api/v1/employees');
// 	console.log(response);
// }
// callAPi();
</script>

<style scoped></style>
