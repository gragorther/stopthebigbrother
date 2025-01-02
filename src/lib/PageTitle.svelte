<script lang="ts">
	interface Props {
		title: string;
	}

	let { title }: Props = $props();
</script>

<h1
	class="bg-gradient-to-r text-transparent bg-clip-text font-extrabold mx-auto my-5 text-center p-2 text-4xl lg:text-6xl text-red-600 leading-relaxed"
>
	{title}
</h1>
<title>GregTech - {title}</title>
