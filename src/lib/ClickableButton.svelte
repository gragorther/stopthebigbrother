<script lang="ts">
	interface Props {
		href?: string; // The URL to navigate to
		children: any;
	}

	let { href = '', children }: Props = $props();
</script>

<a
	{href}
	class="text-white hover:text-white bg-red-600 text-base rounded-sm p-1 hover:bg-red-400 flex items-stretch"
	target="_blank">{@render children?.()}</a
>
