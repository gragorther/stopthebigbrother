<script lang="ts">
	import Blog from '$lib/Blog.svelte';
	import PageTitle from '$lib/PageTitle.svelte';

	const posts: any = [];
</script>

<PageTitle title="Blog" />
<div class="flex flex-wrap gap-6 justify-center">
	{#each posts as post}
		<Blog link={post.link} image={post.image} title={post.title} previewText={post.previewText} />
	{/each}
</div>
