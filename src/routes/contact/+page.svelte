<script>
	import ClickableButton from '$lib/ClickableButton.svelte';
	import DualImage from '$lib/DualImage.svelte';
	import PageTitle from '$lib/PageTitle.svelte';
</script>

<PageTitle title="Contact" />

<ul>
	<div class="flex flex-wrap gap-2 justify-center">
		<li>
			<ClickableButton href="https://blog.gregtech.eu/contact"
				><DualImage
					classes="rounded-full"
					imgSrc="https://blog.gregtech.eu/favicon.png"
					imgAlt="GregTech logo">GregTech</DualImage
				></ClickableButton
			>
		</li>
		<li>
			<ClickableButton href="https://danpodjed.eu"
				><DualImage imgSrc="/danpodjed.jpg">Dan Podjed</DualImage></ClickableButton
			>
		</li>
	</div>
</ul>
