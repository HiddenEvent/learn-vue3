<template>
	<div>
		<TheNav></TheNav>
		<TheView></TheView>
		<hr />
		<FancyButton>Click <span style="color: red">@@</span> </FancyButton>
		<FancyButton></FancyButton>
	</div>
</template>

<script>
import TheNav from './components/TheNav.vue';
import TheView from './components/TheView.vue';
import FancyButton from './components/FancyButton.vue';
import { inject } from 'vue';

export default {
	components: {
		TheNav,
		TheView,
		FancyButton,
	},
	setup() {
		const msg = inject('msg');
		console.log(msg);
		return {};
	},
};
</script>
