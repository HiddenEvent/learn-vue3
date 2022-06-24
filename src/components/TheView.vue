<template>
	<main>
		<div class="container">
			<div class="row">
				<div class="col col4" v-for="post in posts" :key="post.id">
					<AppCard :title="post.title" :contents="post.contents" :type="post.type" :isLike="post.isLike"></AppCard>
				</div>
			</div>
		</div>
	</main>
</template>

<script>
import { reactive } from 'vue';

export default {
	setup() {
		const posts = reactive([
			{ id: 1, title: '제목1', contents: '내용1', isLike: true, type: 'news' },
			{ id: 2, title: '제목2', contents: '내용2', isLike: true, type: 'news' },
			{ id: 3, title: '제목3', contents: '내용3', isLike: false, type: 'notice' },
			{ id: 4, title: '제목4', contents: '내용4', isLike: true, type: 'news' },
		]);
		return { posts };
	},
};
</script>
