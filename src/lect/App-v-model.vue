<template>
	<h2>체크박스 양방향</h2>
	<label for="checkbox">{{ checkBoxValue }}</label>
	<input type="checkbox" id="checkbox" v-model="checkBoxValue" />
	<h2>라디오 양방향</h2>
	<label>
		<input type="radio" name="type" value="O" v-model="radioValue" />
		O형
	</label>
	<label>
		<input type="radio" name="type" value="A" v-model="radioValue" />
		A형
	</label>
	<label>
		<input type="radio" name="type" value="B" v-model="radioValue" />
		B형
	</label>
	<div>{{ radioValue }}</div>
	<h2>셀렉트 양방향</h2>
	<select v-model="selectValue">
		<option value="html">html</option>
		<option value="css">css</option>
		<option value="javascript">javascript</option>
	</select>
	<div>{{ selectValue }}</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		const checkBoxValue = ref(false);
		const radioValue = ref('O');
		const selectValue = ref('javascript');
		return { checkBoxValue, radioValue, selectValue };
	},
};
</script>
