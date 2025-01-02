<script lang="ts">
	interface Props {
		children?: any;
		href?: string;
	}
	let { children, href }: Props = $props();
</script>

<a
	{href}
	class="border-solid border-white border-2 rounded-sm bg-red-600 text-xl p-2 text-center hover:bg-red-400 text-white mr-2 sm:text-lg sm:p-3 lg:text-xl lg:p-1 hover:text-white"
>
	{@render children?.()}
</a>
